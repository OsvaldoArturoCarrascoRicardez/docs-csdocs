---
title: Guía de Estilo de Documentación
description: Estándares y formatos para la documentación de CSDOCS.
---

# Guía de Estilo

Esta guía establece los estándares para escribir y estructurar la documentación de CSDOCS.

## Estructura de Directorios

- **`src/content/docs/usuario/`**: Manuales dirigidos a usuarios finales.
- **`src/content/docs/tecnico/`**: Documentación para desarrolladores y administradores (Instalación, Backend, Frontend).

## Formato de Manuales (Frontend/Backend)

Los manuales deben seguir esta estructura:

1.  **Título y Descripción Corta**
2.  **Contexto de la Suite**: Explicar dónde encaja el componente.
3.  **Tabla de Contenidos**: Enlaces ancla.
4.  **Características Principales**: Lista con emojis (✅).
5.  **Guía de Desarrollo/Uso**:
    *   Requisitos
    *   Instalación
    *   Ejecución
6.  **Configuración**: Variables, estilos.
7.  **Uso de Agentes de IA**: Referencia a `AGENTS.MD`.
8.  **Footer**: "Desarrollado por [CSDocs]".

## Componentes MDX

### Accordion (Preguntas Frecuentes)

```mdx
import Accordion from "../../../components/Accordion.astro";

<Accordion title="¿Pregunta?">
  Respuesta detallada.
</Accordion>
```

### Cards

```mdx
import { Card } from "@astrojs/starlight/components";

<Card title="Título" icon="star">
  Contenido.
</Card>
```

## Convenciones

- **Idioma**: Español (Neutro).
- **Código**: Bloques con resaltado de sintaxis (```bash, ```json).
- **Rutas**: Siempre usar rutas relativas o absolutas desde la raíz del sitio.

---

**Nota**: Mantén esta guía actualizada con cualquier nuevo estándar.
