# 📱 QR Generator Pro - Premium Edition

![Version](https://img.shields.io/badge/version-1.0.0-blueviolet) ![Status](https://img.shields.io/badge/status-stable-success) ![License](https://img.shields.io/badge/license-MIT-gray)

**QR Generator Pro** es una aplicación web moderna, responsive y de alto rendimiento diseñada para generar códigos QR de forma instantánea. A diferencia de los generadores básicos, esta herramienta se centra en una **Experiencia de Usuario (UX) Premium**, utilizando diseño **Glassmorphism**, micro-interacciones animadas y notificaciones elegantes (Toasts) en lugar de alertas nativas.

---

## ✨ Características Principales

* **🎨 Diseño UI/UX Senior:** Interfaz limpia con efectos de desenfoque (backdrop-filter), sombras suaves y paleta de colores moderna (Indigo + Pink).
* **📱 Totalmente Responsive:** Diseño "Mobile-First". En escritorio se ve elegante, y en móviles los controles se adaptan a una rejilla táctil optimizada para el pulgar.
* **⚡ Generación Instantánea:** Crea QRs para:
    * 🔗 **URLs:** Enlaces web directos.
    * 📝 **Texto:** Mensajes ocultos o información plana.
    * 👤 **vCard:** Tarjetas de contacto que se guardan automáticamente en la agenda al escanear.
    * ☁️ **Archivos (Beta):** Subida de imágenes/videos temporales (vía API externa).
* **🔔 Sistema de Notificaciones:** Reemplazo de `alert()` por "Toasts" animados que informan de errores o éxitos de forma no intrusiva.
* **✨ Animaciones:** Transiciones suaves, loaders de carga y efectos al pasar el mouse (hover states).

---

## 🛠️ Tecnologías Utilizadas

El proyecto ha sido construido utilizando estándares web modernos sin dependencias pesadas de frameworks (Vanilla JS):

* **HTML5:** Estructura semántica.
* **CSS3:** Variables CSS (:root), Flexbox, Grid Layout, Animaciones (@keyframes) y Media Queries.
* **JavaScript (ES6+):** Lógica asíncrona (`async/await`) para subidas, manipulación del DOM y gestión de eventos.
* **Librerías Externas:**
    * `qrcode.js`: Para la renderización del código QR.
    * `FontAwesome 6`: Para la iconografía.
    * `Google Fonts`: Tipografías Inter y Poppins.
* **API:** `file.io` (para el alojamiento temporal de archivos subidos).

---

## 🚀 Instalación y Uso

Debido a las políticas de seguridad de los navegadores modernos (CORS), este proyecto tiene requerimientos específicos para funcionar al 100%.

### 1. Clona o Descarga
Descarga el archivo `index.html` y colócalo en una carpeta de tu ordenador.

### 2. Ejecución (Importante ⚠️)

#### ❌ Opción A: Doble Click (No recomendado)
Si haces doble click en `index.html`, la página se abrirá, pero **la función de "Subir Archivo" FALLARÁ**.
* *Razón:* Los navegadores bloquean las peticiones a internet desde archivos locales (`file://`).

#### ✅ Opción B: Live Server (Recomendado para VS Code)
1.  Abre la carpeta del proyecto en **Visual Studio Code**.
2.  Instala la extensión **"Live Server"**.
3.  Haz click derecho en `index.html` y selecciona **"Open with Live Server"**.
4.  La app funcionará perfectamente en `http://127.0.0.1:5500`.

#### ✅ Opción C: Subirlo a Internet
Sube el archivo `index.html` a cualquier hosting estático gratuito:
* GitHub Pages
* Netlify
* Vercel

---

## 📂 Estructura del Código

El proyecto está contenido en un único archivo (`index.html`) para facilitar la portabilidad, pero está estructurado internamente así:

1.  **`<head>` & Styles:**
    * Definición de variables CSS (`--primary`, `--glass-bg`).
    * Estilos base y reset.
    * Componentes (Botones, Inputs, Cards).
    * Animaciones.
2.  **`<body>` HTML:**
    * Contenedor `app-container`.
    * Sistema de Tabs.
    * Secciones de Inputs (`input-group`).
    * Área de resultados (`qr-wrapper`).
3.  **`<script>` JS:**
    * Configuración global.
    * Funciones de UI (`setTab`, `showToast`).
    * Lógica de negocio (`generate`, `createQR`).
    * Manejo de API (`fetch` a file.io).

---

## 🎨 Personalización

Puedes cambiar fácilmente el aspecto visual editando las variables CSS al inicio del `<style>`:

```css
:root {
    --primary: #6366f1;       /* Color principal */
    --secondary: #ec4899;     /* Color de acento */
    --bg-gradient: ...;       /* Fondo de la página */
    --radius: 16px;           /* Redondeo de bordes */
}
