# prediccion-tick

Repo **público** mínimo: llama por GET, cada 5 minutos, al tick de producción de la Mesa (`/api/paper/tick`) y, cada 30 minutos, al vigilante (`/api/paper/watchdog`).

No contiene el código de la app ni secretos. Solo hay dos workflows de GitHub Actions que hacen `curl` al endpoint ya desplegado.

## Secretos (Settings → Secrets and variables → Actions)

- `APP_URL`: URL de producción, `https://…`, **sin** barra final.
- `CRON_SECRET`: el mismo bearer que ya usa el tick. No lo pongas en issues, en el chat ni en este repo.

Los logs de un repo público son visibles para cualquiera: los workflows no imprimen el cuerpo de la respuesta ni los secretos.

## Inactividad de 60 días

En un repositorio público, GitHub desactiva los workflows programados si no hay actividad del repo en 60 días. Un commit o un issue de vez en cuando evitan el corte. Para reactivar: Actions → el workflow → Enable workflow.
