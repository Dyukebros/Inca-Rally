# Inca Rally · versión web para Vercel

Esta carpeta es la web completa del juego. No necesita compilar nada: Vercel la sirve tal cual.

- `index.html`: el juego entero (tramos, circuitos, concesionario, taller y modo online).
- `vercel.json`: configuración mínima del proyecto.

## Publicarla en Vercel

### Opción A: desde el navegador, sin instalar nada

1. Crea un repositorio nuevo en GitHub llamado `inca-rally`.
2. En el repositorio, pulsa **Add file › Upload files** y sube `index.html`, `vercel.json` y este `README.md`.
3. Entra en vercel.com con tu cuenta y pulsa **Add New › Project**.
4. Importa el repositorio `inca-rally`. En **Framework Preset** deja **Other** y pulsa **Deploy**.
5. En menos de un minuto tendrás la web en una dirección del tipo `inca-rally.vercel.app`. Si ese nombre ya está cogido, Vercel añade unas letras al final; puedes cambiarlo en **Settings › Domains**.

Cada vez que subas una versión nueva de `index.html` al repositorio, Vercel la publica sola.

### Opción B: con la terminal

Con Node.js instalado, dentro de esta carpeta:

```
npx vercel deploy --prod
```

La primera vez te pedirá iniciar sesión en Vercel en el navegador y confirmar el nombre del proyecto.

## Cómo funciona el modo online en la web

En la versión de Vercel, las carreras online conectan a los jugadores directamente entre sus navegadores (WebRTC, con PeerJS). Para presentarse unos a otros se usa el servidor público gratuito de PeerJS.

- Quien crea la sala es el anfitrión. Si cierra la página, la sala se cierra para todos.
- Caben hasta 12 pilotos por sala.
- Algunas redes muy cerradas (de empresa, por ejemplo) bloquean estas conexiones. En casa y con datos móviles suele funcionar sin problema.

Dentro de Claude, el mismo juego usa la sala compartida de Claude, y ahí solo pueden entrar personas que tengan acceso a la página.

Los récords, el dinero y el garaje se guardan en el navegador de cada jugador.
