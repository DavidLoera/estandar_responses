# Estándar de respuestas de error

Las respuestas de error deben seguir un formato uniforme para facilitar
el manejo en frontends, logs y herramientas de monitoreo.

## Estructura base

```json
{
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "Datos de entrada no válidos",
    "details": [
      {
        "field": "name",
        "message": "El nombre es obligatorio"
      }
    ]
  },
  "meta": {
    "timestamp": "2025-01-01T12:00:00Z",
    "correlationId": "uuid",
    "version": "v1"
  }
}
```

## Campos

- `error.code`: código interno en `UPPER_SNAKE_CASE`.
- `error.message`: mensaje legible para humanos.
- `error.details`: lista opcional con detalles específicos (por ejemplo, errores de validación).
- `meta.timestamp`: fecha/hora en ISO 8601 (UTC).
- `meta.correlationId`: identificador único para trazabilidad.
- `meta.version`: versión de la API que responde.

## Códigos de error sugeridos

- `VALIDATION_ERROR`
- `AUTHENTICATION_FAILED`
- `AUTHORIZATION_FAILED`
- `RESOURCE_NOT_FOUND`
- `CONFLICT`
- `INTERNAL_ERROR`
