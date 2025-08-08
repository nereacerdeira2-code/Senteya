<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Senteya - Red Social de Sentimientos</title>

  <!-- Manifest -->
  <link rel="manifest" href="manifest.json" />

  <!-- Tailwind y Fonts -->
  <script src="https://cdn.tailwindcss.com"></script>
  <link rel="stylesheet" href="styles.css">
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
  <meta name="theme-color" content="#8b5cf6"/>
</head>
<body class="bg-gray-50 font-inter min-h-screen flex flex-col items-center justify-center">
  <main class="bg-white p-8 rounded-lg shadow-md w-full max-w-md">
    <h1 class="text-3xl font-bold text-purple-600 mb-6 text-center">Senteya</h1>
    <p class="text-gray-600 mb-6 text-center">Conecta corazones, comparte sentimientos</p>

    <button onclick="enviarSentimiento()">Compartir sentimiento</button>
    <p id="respuesta" class="mt-4 text-green-600"></p>
  </main>

  <script src="app.js"></script>
</body>
</html>
body {
  margin: 0;
  padding: 2rem;
  font-family: 'Inter', sans-serif;
  background-color: #f0f4ff;
  color: #333;
  text-align: center;
}

h1 {
  color: #8b5cf6;
  font-size: 2rem;
}

button {
  background-color: #8b5cf6;
  color: white;
  padding: 1rem 2rem;
  border: none;
  border-radius: 10px;
  font-size: 1rem;
  margin-top: 1rem;
  cursor: pointer;
}

button:hover {
  background-color: #7c3aed;
}
function enviarSentimiento() {
  const respuesta = document.getElementById('respuesta');
  respuesta.innerText = '¡Gracias por compartir tu sentimiento!';
}

if ('serviceWorker' in navigator) {
  navigator.serviceWorker.register('sw.js')
    .then(() => console.log('Service Worker registrado'))
    .catch(error => console.log('Error registrando SW:', error));
}
{
  "name": "Senteya – Red Social de Sentimientos",
  "short_name": "Senteya",
  "description": "Conecta corazones, comparte sentimientos",
  "start_url": "/",
  "display": "standalone",
  "background_color": "#f8fafc",
  "theme_color": "#8b5cf6",
  "orientation": "portrait",
  "icons": [
    {
      "src": "icon-192.png",
      "sizes": "192x192",
      "type": "image/png"
    },
    {
      "src": "icon-512.png",
      "sizes": "512x512",
      "type": "image/png"
    }
  ],
  "categories": ["social", "lifestyle", "health"],
  "lang": "es",
  "dir": "ltr"
}
self.addEventListener('install', event => {
  event.waitUntil(
    caches.open('senteya-cache-v1').then(cache => {
      return cache.addAll([
        '/',
        '/index.html',
        '/styles.css',
        '/app.js',
        '/manifest.json',
        '/icon-192.png',
        '/icon-512.png'
      ]);
    })
  );
});

self.addEventListener('fetch', event => {
  event.respondWith(
    caches.match(event.request).then(response => {
      return response || fetch(event.request);
    })
  );
});
