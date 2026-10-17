# status

Monitoreo externo de Home2Health. Cada 5 minutos, desde GitHub Actions (fuera del
VPS), revisa:

- `https://api.home2health.care/health` (joey, incluye la base)
- `https://admin.home2health.care/` (monica)
- `https://app.home2health.care/` (ross)
- `https://files.home2health.care/minio/health/live` (MinIO)

Cada URL tiene 3 intentos. Si alguna sigue caída, se abre **un** issue con la
etiqueta `down` y GitHub avisa por correo a quienes siguen el repo. Al
recuperarse, el issue se cierra solo. El historial de caídas son los issues
cerrados.
