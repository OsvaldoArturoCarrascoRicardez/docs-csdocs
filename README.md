# CSDOCS Documentation

Este repositorio contiene el código fuente y el contenido del **Centro de Documentación de CSDOCS**, construido con [Astro Starlight](https://starlight.astro.build).

## 🚀 Inicio Rápido

### Requisitos Previos

- Node.js v20+ (Recomendado v22)
- npm

### Instalación

1. Clonar el repositorio:
   ```bash
   git clone <url-del-repo>
   cd docs-csdocs
   ```

2. Instalar dependencias:
   ```bash
   npm install
   ```

3. Iniciar el servidor de desarrollo:
   ```bash
   npm run dev
   ```

El sitio estará disponible en `http://localhost:4321`.

## Estructura del Proyecto

El proyecto sigue la estructura estándar de Astro Starlight, adaptada para CSDOCS:

```text
├── public/                 # Archivos estáticos
│   └── favicon/            # Iconos del sitio
├── src/
│   ├── assets/             # Imágenes y medios (Referenciados en MDX)
│   ├── config/             # Configuración del sitio
│   │   ├── config.json     # Título, logo, settings generales
│   │   ├── sidebar.json    # Estructura del menú lateral
│   │   └── locals.json     # Configuración de idiomas (Español)
│   ├── content/
│   │   └── docs/           # Contenido de la documentación
│   │       ├── guias/      # Guías y tutoriales
│   │       ├── manuales/   # Manuales específicos (Core, CG, Archivística, Content)
│   │       └── referencia/ # Referencia técnica
│   └── styles/             # CSS global y personalizaciones
└── astro.config.mjs        # Configuración de Astro
```

## 📝 Editando Contenido

### Agregar una nueva página

Crea un archivo `.md` o `.mdx` en la carpeta correspondiente dentro de `src/content/docs/`.

**Ejemplo:** `src/content/docs/guias/nueva-guia.md`

```markdown
---
title: Título de la Guía
description: Descripción breve para SEO y tarjetas.
---

Contenido de la guía en formato Markdown...
```

### Imágenes

Las imágenes deben ubicarse en `src/assets/`. Para usarlas en markdown:

```markdown
![Texto alternativo](../../../assets/imagen.png)
```

## 🛠 Comandos Disponibles

| Comando          | Acción                                         |
| :--------------- | :--------------------------------------------- |
| `npm run dev`    | Inicia el servidor de desarrollo local.        |
| `npm run build`  | Genera el sitio estático para producción.      |
| `npm run preview`| Previsualiza el build de producción localmente.|

## � Enlaces Útiles

- [Documentación de Astro](https://docs.astro.build)
- [Documentación de Starlight](https://starlight.astro.build)
