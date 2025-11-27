# Versionado y metadatos

Todas las respuestas deben incluir la sección `meta` con información común.

## Estructura recomendada

```json
{
  "meta": {
    "timestamp": "2025-01-01T12:00:00Z",
    "version": "v1",
    "correlationId": "uuid-opcional"
  }
}
```

- `timestamp`: fecha/hora en UTC, formato ISO 8601.
- `version`: versión pública de la API (por ejemplo, `v1`, `v2`).
- `correlationId`: identificador único para rastrear la petición de extremo a extremo.

Se recomienda generar el `correlationId` desde el API Gateway o middleware
de entrada y propagarlo a los microservicios.
