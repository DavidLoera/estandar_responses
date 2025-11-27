# Estándar de paginación

Las operaciones que devuelvan colecciones deben soportar paginación
consistente.

## Parámetros de entrada

- `page`: número de página (1-based).
- `size`: tamaño de página.
- `sort`: campo de ordenamiento.
- `order`: dirección (`asc` o `desc`).

Ejemplo:

```
GET /api/v1/products?page=1&size=10&sort=price&order=asc
```

## Estructura de respuesta

```json
{
  "data": [
    { "id": "123", "name": "Product 1" }
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
