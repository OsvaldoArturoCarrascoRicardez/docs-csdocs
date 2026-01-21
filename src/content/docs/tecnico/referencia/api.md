---
title: Referencia de API
description: Documentación técnica de las APIs de CSDocs.
---

La Suite CSDocs expone servicios REST para la integración con otros sistemas.

## Autenticación

Todas las peticiones deben incluir el header `Authorization: Bearer <token>`.

## Endpoints Base

- **Core**: `https://api.csdocs.com/core/v1`
- **Content**: `https://api.csdocs.com/content/v1`

## Ejemplo de Llamada

```bash
curl -X GET "https://api.csdocs.com/core/v1/users" \
     -H "Accept: application/json" \
     -H "Authorization: Bearer {TOKEN}"
```
