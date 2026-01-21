---
title: Archivística Frontend
---

Este proyecto es la interfaz de usuario moderna diseñada para la gestión integral de archivonomía. Construida sobre **Angular 18**, esta plataforma permite a los usuarios interactuar con el ciclo de vida de los documentos y expedientes de manera intuitiva.

## Suite CSDocs

La suite CSDocs está integrada por soluciones especializadas que cubren todo el ciclo de vida de la información:

### 🛡️ Core

Motor central que gestiona usuarios, dominios y estructura organizacional global.

### 🏛️ Archivística

Gestión integral del marco archivístico institucional:

- **Ciclo de Vida**: Control de fases de trámite, concentración e histórico.
- **Normativa**: Alineada con la **Ley General de Archivos**.
- **Gestión de Expedientes**: Visualización y edición de legajos y documentos.

---

## 📋 Tabla de Contenidos

- [Características Principales](#-características-principales)
- [Guía de Desarrollo](#-guía-de-desarrollo)
- [Configuración de Estilos](#-configuración-de-estilos)
- [Configuración de Entornos](#-configuración-de-entornos)
- [Compilación CKEditor](#-compilación-ckeditor)
- [Uso de Agentes de IA](#-uso-de-agentes-de-ia)

---

## ✨ Características Principales

- ✅ **Angular 18 & Material Design**: Interfaz moderna y accesible.
- ✅ **Gestión de Expedientes**: Edición completa de legajos.
- ✅ **Editor Avanzado**: Integración con CKEditor 5 para documentos.
- ✅ **Visor PDF**: Visualización integrada de documentos.

---

## 🛠️ Guía de Desarrollo

### Requisitos Previos

- **Node.js**: v20.x (Recomendado usar `nvm use 20`)
- **Angular CLI**: v18.x

### Instalación de Dependencias

```bash
npm install --legacy-peer-deps
```

### Servidor de Desarrollo

Ejecuta `ng serve` para un servidor local. Navega a `http://localhost:4200/`.

### Construcción

Ejecuta `ng build` para compilar el proyecto. Los archivos se guardarán en `dist/`.

---

## 🎨 Configuración de Estilos

El sistema utiliza Material Design. Para personalizar:

1. Utiliza [Palette Generator](http://mcg.mbitson.com/).
2. Copia `src/assets/scss/_material.example.scss` a `src/assets/scss/_material.scss`.
3. Actualiza los valores.

---

## 🔧 Configuración de Entornos

Configura las URLs de los servicios en `src/assets/config.json`:

```json
{
  "production": false,
  "apiUrl": "http://localhost:8000",
  "apiUrlCG": "http://localhost:8002",
  "pdfjsAssetsPath": "/assets/pdfjs/"
}
```

---

## 📝 Compilación CKEditor

La aplicación utiliza una versión personalizada de CKEditor 5:

1. Navega a `src/assets/ckeditor5-build-decoupled-document` (o la ruta correspondiente en `projects/editor`).
2. Instala: `npm install --legacy-peer-deps`.
3. Compila: `npm run build`.

---

## 🤖 Uso de agentes de IA

- Las políticas y reglas para el uso de agentes de IA están centralizadas en `AGENTS.MD`.
- Antes de usar un agente, revisa `AGENTS.MD`.

---

**Desarrollado por:** [CSDocs]
**Documentación:** Archivística

---

<p align="center">
✨ <strong>Archivística - Gestión Documental y Archivonomía</strong> ✨
</p>
