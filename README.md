```markdown
# estandar_responses

Colección de plantillas y respuestas estandarizadas (JSON, YAML, Markdown) para usar en chatbots, APIs, correos, documentación y otras integraciones.

Este repositorio sirve como biblioteca centralizada de mensajes y respuestas reutilizables para proyectos que necesitan consistencia en tono, estructura y localización.

## Contenido principal
- Plantillas de respuesta (success, error, validation, info).
- Ejemplos en JSON y YAML.
- Guías rápidas de integración para frontend, backend y bots.
- Convenciones de localización (i18n).

## Ejemplos de uso

Ejemplo simple (JSON):
```json
{
  "id": "user_not_found",
  "status": "error",
  "http_code": 404,
  "title": "Usuario no encontrado",
  "message": "No pudimos encontrar un usuario con los criterios proporcionados.",
  "suggestions": [
    "Verifica que el ID del usuario sea correcto.",
    "Intenta realizar la búsqueda con otro criterio."
  ]
}
```

Ejemplo simple (YAML):
```yaml
- id: user_created
  status: success
  http_code: 201
  title: "Usuario creado"
  message: "El usuario fue creado correctamente."
  metadata:
    retry: false
```

Ejemplo de integración (Node.js - pseudocódigo):
```js
const templates = require('./templates/json/user_responses.json');

function sendError(res, templateId, details) {
  const t = templates.find(x => x.id === templateId);
  res.status(t.http_code).json({ ...t, details });
}
```

## Convenciones sugeridas
- id: identificador único (snake_case).
- status: success | error | warning | info.
- http_code: código HTTP sugerido (opcional).
- title: título corto, amigable.
- message: mensaje principal.
- suggestions: (opcional) lista de acciones recomendadas.
- metadata: (opcional) campo libre para datos adicionales.

## Estructura propuesta del repositorio
- templates/
  - json/
  - yaml/
  - md/
- locales/
  - es/
  - en/
- examples/
- CONTRIBUTING.md
- LICENSE

## Cómo empezar
1. Clona el repositorio:
   git clone https://github.com/DavidLoera/estandar_responses.git
2. Copia las plantillas que necesites a tu proyecto y adáptalas según las convenciones.
3. Abre un PR si agregas plantillas nuevas o mejoras las existentes.

## Contribuir
- Añade plantillas en la carpeta `templates/` siguiendo las convenciones.
- Incluye pruebas o ejemplos en `examples/` cuando corresponda.
- Agrega descripción clara en el commit y referencia la plantilla/modificación.
- Lee y sigue las guías en `CONTRIBUTING.md` (si no existe, crea una simple).

## Licencia
Este repositorio no tiene licencia especificada. Si quieres que lo publique bajo MIT u otra licencia, añade un archivo `LICENSE` con la licencia deseada.

## Contacto
Mantenedor: @DavidLoera  
Para dudas o propuestas: abre una Issue o envía un Pull Request.
```
