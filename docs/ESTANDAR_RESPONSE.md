# Estándar de respuestas de la API

Este documento define el formato estándar de las respuestas JSON para los
microservicios de la empresa.

## Convenciones generales

- `Content-Type: application/json; charset=utf-8`.
- Campos en `camelCase`.
- Mantener una estructura clara basada en:
  - `data`: información principal.
  - `pagination`: información de paginación (cuando aplique).
  - `error`: información de error (cuando aplique).
  - `meta`: metadatos comunes.

Una respuesta debe tener **o** `data` **o** `error`, nunca ambos.

## Respuesta exitosa (recurso único)

```json
{
  "data": {
    "id": "123",
    "name": "Product Name",
    "price": 100.0
  },
  "meta": {
    "timestamp": "2025-01-01T12:00:00Z",
    "version": "v1"
  }
}
```

## Respuesta exitosa (colección paginada)

```json
{
  "data": [
    { "id": "123", "name": "Product 1", "price": 100.0 },
    { "id": "124", "name": "Product 2", "price": 150.0 }
  ],
  "pagination": {
    "page": 1,
    "size": 10,
    "totalElements": 42,
    "totalPages": 5
  },
  "meta": {
    "timestamp": "2025-01-01T12:00:00Z",
    "version": "v1"
  }
}
```

## Respuesta de error

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
    "correlationId": "f2d1c1c0-1a2b-3c4d-5e6f-7890abcdef12",
    "version": "v1"
  }
}
```

Usa estos ejemplos como referencia visual y combínalos con los otros
documentos de `docs/` para casos específicos.
