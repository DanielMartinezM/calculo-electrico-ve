# Eléctrico VE — proyecto Android (Capacitor)

La app es 100 % local (HTML/JS), funciona sin internet. Todo el código está en `www/index.html`.

## Opción A — Sin instalar nada: APK en GitHub (recomendada)
1. Crea un repositorio nuevo en github.com y sube esta carpeta completa (incluida `.github`).
2. En el repositorio: pestaña **Actions → Construir APK → Run workflow**.
3. Al terminar (unos 5–8 min), abre la ejecución y descarga el artefacto **electrico-ve-apk** (contiene `app-debug.apk`).
4. Pásalo al teléfono, ábrelo y acepta "instalar apps de orígenes desconocidos".

## Opción B — En tu PC (necesita Node 18+, JDK 17 y Android Studio)
```
npm install
npx cap add android
npm run icons
npx cap sync android
npx cap open android      # Android Studio: Build > Build APK(s)
```
Cada vez que cambies `www/index.html` ejecuta `npx cap sync android` y vuelve a compilar.

## Opción C — Sin APK: instalar como PWA
Sube `www/` a un hosting HTTPS (GitHub Pages, Netlify). En Chrome del teléfono: menú ⋮ → **Instalar app**.

## Para publicar en Play Store
El APK "debug" sirve para uso propio. Para la tienda hay que generar un **AAB firmado**
(Android Studio: Build > Generate Signed Bundle) con tu propia clave. Guarda esa clave: sin ella no podrás actualizar la app.
