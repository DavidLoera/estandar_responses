# response_estandar

Este repositorio define el **estándar de respuesta** para todos los microservicios
de la empresa. La idea es que cualquier servicio pueda copiar estos ejemplos
y estructuras para responder de forma consistente.

Contiene:

- `docs/`: documentación de los estándares (estructura general, errores, paginación, etc.).
- `examples/`: ejemplos de respuestas reales en formato JSON.
- `schemas/`: JSON Schemas para validar las respuestas.

Recomendación para GitHub Copilot:
> Cuando generes endpoints nuevos, indica en tu prompt que se deben seguir
> los estándares definidos en estos archivos (especialmente `docs/ESTANDAR_RESPONSE.md`
> y `docs/ERROR_RESPONSE_STANDARD.md`).
