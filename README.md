# Senteya
Red social para compartir sentimientos y conectar corazones
<!DOCTYPE html>
<html lang="es">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width,initial-scale=1.0"/>
    <title>Senteya - Red Social de Sentimientos</title>
    <link rel="manifest" href="manifest.json" />
    <link rel="stylesheet" href="https://cdn.tailwindcss.com" />
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" />
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <meta name="theme-color" content="#8b5cf6"/>
  </head>
  <body class="bg-gray-50 font-inter min-h-screen flex flex-col items-center justify-center">
    <main class="bg-white p-8 rounded-lg shadow-md w-full max-w-md">
      <h1 class="text-3xl font-bold text-purple-600 mb-6 text-center">Senteya</h1>
      <p class="text-gray-600 mb-6 text-center">Conecta corazones, comparte sentimientos</p>
      <!-- Aquí va el contenido de tu red social -->
    </main>
    <script>
      if ('serviceWorker' in navigator) {
        navigator.serviceWorker.register('/sw.js')
          .then(function(registration) {
            console.log('Service Worker registrado con éxito:', registration.scope);
          })
          .catch(function(error) {
            console.log('Error al registrar el Service Worker:', error);
          });
      }
    </script>
  </body>
</html>
{
  "name": "Senteya – Red Social de Sentimientos",
  "short_name": "Senteya",
  "start_url": "/",
  "display": "standalone",
  "background_color": "#ffffff",
  "theme_color": "#8b5cf6",
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
  ]
}
/* styles.css */
body {
  margin: 0;
  padding: 2rem;
  font-family: Arial, sans-serif;
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
      "src": "data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTkyIiBoZWlnaHQ9IjE5MiIgdmlld0JveD0iMCAwIDE5MiAxOTIiIGZpbGw9Im5vbmUiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxyZWN0IHdpZHRoPSIxOTIiIGhlaWdodD0iMTkyIiByeD0iNDAiIGZpbGw9IiM4YjVjZjYiLz4KPHN2ZyB4PSI0OCIgeT0iNDgiIHdpZHRoPSI5NiIgaGVpZ2h0PSI5NiIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSJ3aGl0ZSI+CjxwYXRoIGQ9Ik0yMC44NCA0LjYxYTUuNSA1LjUgMCAwIDAtNy43OCAwTDEyIDUuNjdsLTEuMDYtMS4wNmE1LjUgNS41IDAgMCAwLTcuNzggNy43OGwxLjA2IDEuMDZMMTIgMjEuMjNsNy43OC03Ljc4IDEuMDYtMS4wNmE1LjUgNS41IDAgMCAwIDAtNy43OHoiLz4KPC9zdmc+Cjwvc3ZnPg==",
      "sizes": "192x192",
      "type": "image/svg+xml"
    },
    {
      "src": "data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNTEyIiBoZWlnaHQ9IjUxMiIgdmlld0JveD0iMCAwIDUxMiA1MTIiIGZpbGw9Im5vbmUiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxyZWN0IHdpZHRoPSI1MTIiIGhlaWdodD0iNTEyIiByeD0iMTA0IiBmaWxsPSIjOGI1Y2Y2Ii8+CjxzdmcgeD0iMTI4IiB5PSIxMjgiIHdpZHRoPSIyNTYiIGhlaWdodD0iMjU2IiB2aWV3Qm94PSIwIDAgMjQgMjQiIGZpbGw9IndoaXRlIj4KPHN0eWxlPi5zdDB7Zm9udC1mYW1pbHk6J0dlb3JnaWEnLHNlcmlmO2ZvbnQtc2l6ZToyNHB4O2ZvbnQtd2VpZ2h0OmJvbGQ7fTwvc3R5bGU+Cjx0ZXh0IHg9IjEyIiB5PSIxNiIgdGV4dC1hbmNob3I9Im1pZGRsZSIgY2xhc3M9InN0MCI+UzwvdGV4dD4KPC9zdmc+Cjwvc3ZnPg==",
      "sizes": "512x512",
      "type": "image/svg+xml"
    }
  ],
  "categories": ["social", "lifestyle", "health"],
  "lang": "es",
  "dir": "ltr"
}
