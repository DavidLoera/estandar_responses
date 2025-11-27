# Mapeo de códigos de estado HTTP

Este documento describe qué códigos HTTP usar para cada tipo de operación.

| Caso                                      | Código | Descripción                                | Ejemplo                       |
|------------------------------------------|--------|--------------------------------------------|--------------------------------|
| Lista de recursos                        | 200    | Petición exitosa                           | GET /api/v1/products          |
| Recurso encontrado                       | 200    | Recurso devuelto correctamente             | GET /api/v1/products/{id}     |
| Recurso creado                           | 201    | Recurso creado correctamente               | POST /api/v1/products         |
| Sin contenido                            | 204    | Operación exitosa sin body                 | DELETE /api/v1/products/{id}  |
| Parámetros inválidos                     | 400    | Error de validación                        | POST /api/v1/products         |
| No autenticado                           | 401    | Faltan credenciales o son inválidas        | Cualquier endpoint protegido  |
| No autorizado                            | 403    | El usuario no tiene permisos               | Recursos restringidos         |
| Recurso no encontrado                    | 404    | El recurso no existe                       | GET /api/v1/products/{id}     |
| Conflicto                                | 409    | Conflicto con el estado del recurso        | POST /api/v1/orders           |
| Error interno                            | 500    | Error no controlado                        | Cualquier endpoint            |
