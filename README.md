# Print Manager 3D — app Android

App de administración de proyectos de impresión 3D empaquetada como app nativa Android (WebView + la app completa embebida, funciona 100% sin internet).

## Cómo obtener el APK

1. Crea un repositorio nuevo en GitHub (puede ser privado) — por ejemplo `print-manager-3d`.
2. Sube **todo el contenido de esta carpeta** a la rama `main` (arrastrar y soltar en la web de GitHub funciona: usa "Add file → Upload files" y sube las carpetas).
3. Ve a la pestaña **Actions**. Se dispara solo el workflow *Build APK*. Tarda ~4 minutos.
4. Cuando termine (palomita verde), tienes el APK en dos lugares:
   - **Releases** (lado derecho del repo) → `print-3d.apk` → descárgalo directo desde el celular.
   - O en Actions → el run → sección *Artifacts* → `print-3d-apk`.
5. En el celular abre el archivo y acepta "Instalar apps de origen desconocido".

## Actualizar la app

Cuando cambie el diseño, reemplaza `app/src/main/assets/index.html` con la versión nueva y haz commit: el workflow genera un APK nuevo automáticamente. Súbele el `versionCode` en `app/build.gradle` si quieres instalar encima sin desinstalar.

## Notas

- El APK está firmado con la llave de depuración: sirve perfecto para instalarlo tú mismo, no para publicar en Google Play. Para Play se necesita una llave propia de release.
- Los datos (pedidos, inventario, clientes, cotizaciones) se guardan localmente en el teléfono.
- El botón **PDF** del cotizador usa el sistema de impresión de Android → "Guardar como PDF", y de ahí lo compartes por WhatsApp.
- ID de la app: `mx.taller3d.printmanager` (cámbialo en `app/build.gradle` y en el paquete de `MainActivity.java` si quieres otro).
