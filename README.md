# Yoan's Web Store: Solución de compatibilidad para ChromeOS 93

## ⬇️ Descargas Oficiales
**[Haz clic aquí para ir a la sección de Releases y descargar la última versión](https://github.com/emanuelyoan470/yoans-web-store/releases/latest)**
*(Recomendamos descargar el archivo `chromewebstore.zip`).*

---

## 📖 Descripción del Proyecto
**Yoan's Web Store** es una adaptación de código abierto de la extensión *Chromium Web Store* (creada originalmente por NeverDecaf). Su propósito es restaurar la funcionalidad de instalación de la Chrome Web Store en navegadores basados en Chromium que han quedado obsoletos, específicamente en equipos con **ChromeOS 93**.

## 🚨 El Problema
Cuando Google deja de dar soporte a una versión de ChromeOS (como la 93), el navegador se vuelve incompatible con los servidores actuales de la Chrome Web Store. Al intentar instalar una extensión, la tienda bloquea el botón y muestra el mensaje: *"Para agregar este elemento a Chrome, actualiza el navegador"*. 

## 💡 ¿Cómo funciona esta solución?
Esta extensión no modifica el sistema operativo. Actúa como un puente de compatibilidad:
1. **Restauración del Botón:** La extensión inyecta scripts en la página de la Chrome Web Store para que la tienda crea que el navegador es una versión moderna, reactivando el botón azul de "Agregar a Chrome".
2. **Descarga Directa:** Al hacer clic, en lugar de fallar, la tienda permite la descarga del paquete de instalación (`.crx`) a tu carpeta de Descargas.
3. **Instalación Manual:** Una vez descargado, el usuario puede instalar el archivo `.crx` usando el Modo Desarrollador de Chrome (arrastrándolo a `chrome://extensions`), evitando el bloqueo de la tienda.

## 🛡️ ¿Por qué es un proyecto seguro? (Auditoría)
Sabemos que instalar extensiones fuera de la tienda oficial genera dudas. Aquí te explicamos por qué este proyecto es transparente y seguro:

*   **Código 100% auditable:** El archivo `.zip` que descargas en la sección de *Releases* **no es un ejecutable cerrado**. Es un archivo comprimido estándar. Cualquier persona puede descomprimirlo y abrir los archivos `.json`, `.js` y `.html` con un editor de texto para revisar exactamente qué hace el código línea por línea.
*   **Sin código malicioso:** Si auditas el código, verás que no contiene rastreadores, mineros de criptomonedas ni scripts para robar datos. Solo utiliza las APIs oficiales de Chrome (`management` y `storage`) para gestionar las descargas.
*   **Código Original Verificable:** Este proyecto es una modificación del código original de [NeverDecaf](https://github.com/NeverDecaf/chromium-web-store). Puedes comparar ambos códigos y notarás que la base es la misma.
*   **Licencia MIT:** Todo el código está protegido y distribuido bajo la licencia MIT, lo que garantiza que es software libre y de código abierto.

## ⚙️ Arquitectura Técnica
El proyecto utiliza la Arquitectura de Extensiones de Chrome (Manifest V3). Emplea un `service_worker` en segundo plano y scripts de contenido (`content_scripts`) que se inyectan únicamente en los dominios de la Chrome Web Store. No recopila información del usuario.

## ⚖️ Créditos y Licencia
Este software es una modificación y adaptación del código original creado por **NeverDecaf**.
*   **Código Original:** [Chromium Web Store](https://github.com/NeverDecaf/chromium-web-store).
*   **Modificaciones y Mantenimiento:** Emanuel Yoan (2026).

Este proyecto se distribuye bajo la **Licencia MIT**. Eres libre de usar, copiar, modificar y distribuir este software, siempre que se mantengan los avisos de derechos de autor originales.
