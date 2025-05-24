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
