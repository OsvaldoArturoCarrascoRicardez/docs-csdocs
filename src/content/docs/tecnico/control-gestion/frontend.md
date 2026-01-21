---
title: Control de Gestión Frontend
---

Este proyecto es la interfaz de usuario de **Control de Gestión**, parte integral de la suite **CSDocs**. Está diseñado
para facilitar la comunicación interna y el despacho de trámites administrativos mediante una experiencia fluida y
profesional.

## Suite CSDocs

La suite CSDocs está integrada por soluciones especializadas que cubren todo el ciclo de vida de la información y los
procesos administrativos:

### 🛡️ Core

Es el motor central de la suite que gestiona la configuración global de usuarios, dominios, instancias, licencias y la
estructura organizacional base.

### 📝 Control Gestión (CG)

Especializada en la gestión de correspondencia y seguimiento de solicitudes:

- **Gestión de Asuntos**: Seguimiento puntual de trámites internos y externos organizados por unidades jerárquicas.
- **Flujos de Turnados**: Asignación y despacho dinámico de asuntos entre departamentos para su atención.
- **Módulo de Oficios**: Potente editor estilo Word para la creación de documentos oficiales que se integran
  automáticamente al flujo de gestión.

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

- ✅ **Interfaz Material Design**: Experiencia de usuario consistente y personalizable.
- ✅ **Editor de Documentos Avanzado**: Integración de CKEditor personalizado para oficios.
- ✅ **Gestión Jerárquica**: Visualización y navegación de la estructura organizacional para turnados.
- ✅ **Dashboard de Seguimiento**: Indicadores visuales sobre el estado de los asuntos y trámites.

---

## 🛠️ Guía de Desarrollo

### Requisitos Previos

- **Node.js**: v22 (Recomendado usar `nvm use 22`)
- **Angular CLI**: v18.2.14

### Instalación de Dependencias

Para instalar las dependencias del proyecto, utiliza el siguiente comando debido a compatibilidad de versiones:

```bash
npm i --legacy-peer-deps
```

### Servidor de Desarrollo

Ejecuta `ng serve` para un servidor local. Navega a `http://localhost:4200/`. La aplicación se recargará automáticamente
al modificar los archivos.

### Construcción

Ejecuta `ng build` para compilar el proyecto. Los archivos resultantes se guardarán en el directorio `dist/`.

---

## 🎨 Configuración de Estilos

El proyecto permite personalizar la paleta de colores según la identidad corporativa:

1. Localiza `src/assets/styles/material.example.scss`.
2. Copia y renómbralo como `material.scss`.
3. Ajusta los colores utilizando herramientas como [Material Design Palette Generator](http://mcg.mbitson.com).

```bash
cp src/assets/styles/material.example.scss src/assets/styles/material.scss
```

---

## 🔧 Configuración de Entornos

El frontend requiere apuntar correctamente a la API del backend:

1. Localiza el archivo de configuración de ejemplo: `src/assets/config.json.example`.
2. Copia este archivo y renómbralo como `config.json` en el mismo directorio.
3. Modifica la propiedad `apiUrl` para que apunte a tu instancia de **Control Gestión Back**:

```json
{
  "production": false,
  "apiUrl": "http://localhost:8000",
  "pdfjsAssetsPath": "/assets/pdfjs/",
  "CGFront": "http://localhost:4200",
  "apiTemp": "http://localhost:3000"
}
```

---

## 📝 Compilación CKEditor

El proyecto utiliza una compilación personalizada de CKEditor 5. Si realizas cambios en el editor:

1. Navega al directorio del build: `cd projects/editor/src/ckeditor5-build-decoupled-document`.
2. Instala dependencias: `npm i --legacy-peer-deps`.
3. Compila: `npm run build`.
4. Regresa a la raíz para que Angular detecte los cambios.

---

## 🤖 Uso de agentes de IA

- Las políticas y reglas para el uso de agentes de IA están centralizadas en `AGENTS.MD`.
- Antes de usar un agente o aceptar cambios generados por IA, revisa `AGENTS.MD` y sigue el proceso de revisión
  descrito.

---

**Desarrollado por:** [CSDocs]  
**Documentación:** Control de Gestión Front

---

<p align="center">
✨ <strong>Control de Gestión - Eficiencia en la Comunicación Institucional</strong> ✨
</p>
