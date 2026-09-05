# Banner

Convierte el móvil en un letrero LED. PWA instalable, funciona sin conexión.

## Qué hace

- **Efectos**: desfile, parpadeo, fijo y animaciones de matriz de puntos (corazón latiendo, caminante)
- **9 tipografías**: Píxel, Arcade, Matriz, Bloque, Rótulo, Estrecha, Negra, Futuro, Redonda
- **Colores**: 7 colores sólidos más multicolor con barrido continuo
- **Brillo**: modo LED y modo neón (núcleo blanco con halo)
- **6 marcos**: industrial, cromo, madera, tubo neón, bombillas de marquesina y sin marco
- Velocidad y tamaño ajustables, todo guardado en el propio dispositivo
- Toca el letrero para pantalla completa; la pantalla no se apaga mientras está encendido

## Publicar en GitHub Pages

```bash
git init
git add .
git commit -m "Banner"
git branch -M main
git remote add origin git@github.com:TU-USUARIO/banner.git
git push -u origin main
```

Luego en el repo: **Settings → Pages → Build and deployment → Deploy from a branch**, rama `main`, carpeta `/ (root)`. En un minuto la app estará en `https://TU-USUARIO.github.io/banner/`.

Todas las rutas del proyecto son relativas, así que funciona igual desde una subcarpeta que desde un dominio propio.

## Instalar en el móvil

Abre la URL de GitHub Pages en el móvil:

- **Android / Chrome**: aparecerá el botón "Instalar app" en el panel de ajustes, o usa "Añadir a pantalla de inicio" desde el menú del navegador.
- **iPhone / Safari**: botón Compartir → "Añadir a pantalla de inicio". Safari no permite la instalación automática; es una limitación de iOS.

## Actualizar la app

El service worker cachea los archivos para que funcione sin conexión. Al publicar cambios, sube el número de versión en `sw.js`:

```js
const CACHE_NAME = 'banner-v4';
```

Así los dispositivos ya instalados descartan el caché antiguo y cargan la versión nueva.

## Archivos

| Archivo | Para qué sirve |
|---|---|
| `index.html` | La app entera: interfaz, estilos y lógica |
| `manifest.json` | Nombre, iconos y modo de presentación de la PWA |
| `sw.js` | Caché offline |
| `icon-192.png`, `icon-512.png` | Iconos de instalación |
| `icon-maskable-192.png`, `icon-maskable-512.png` | Iconos con zona de seguridad para Android |
| `apple-touch-icon.png` | Icono para iOS |
