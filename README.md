<!-- public/index.html -->
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Electrodomésticos App</title>
  <link rel="manifest" href="manifest.json">
</head>
<body>
  <div id="root"></div>
  <script>
    // Registrar Service Worker para funcionar offline
    if ('serviceWorker' in navigator) {
      navigator.serviceWorker.register('sw.js');
    }
  </script>
</body>
</html># N4cky1.github.io
// public/manifest.json
{
  "name": "ElectroApp",
  "short_name": "Electro",
  "start_url": "/",
  "display": "standalone",
  "background_color": "#2c3e50",
  "theme_color": "#2c3e50",
  "icons": [
    {
      "src": "icon-192x192.png",
      "sizes": "192x192",
      "type": "image/png"
    }
  ]
}// public/sw.js
self.addEventListener('install', (event) => {
  event.waitUntil(
    caches.open('electro-v1').then((cache) => {
      return cache.addAll([
        '/',
        '/index.html',
        '/src/App.jsx',
        '/database/electro.db'
      ]);
    })
  );
});
