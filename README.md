# 🏆 FirstWin — Predictor de Partidos

App de predicciones de fútbol sin backend. Los puntos se editan manualmente en `data.json` y se sirve directo desde GitHub Pages.

---

## 📁 Estructura del proyecto

```
firstwin/
├── index.html          ← Login
├── partidos.html       ← Partidos y predicciones
├── tabla.html          ← Tabla de posiciones
├── perfil.html         ← Perfil del usuario
├── data.json           ← ⭐ AQUÍ se editan los puntos
├── CSS/
│   └── Predicciones.css
└── Imagenes/
    └── *.jpg
```

---

## ✏️ Cómo editar puntos (Admin)

Abre `data.json` en GitHub y modifica el valor de `"puntos"` para cada jugador:

```json
{
  "jugadores": [
    { "usuario": "rayc",   "puntos": 7 },
    { "usuario": "eduah",  "puntos": 4 },
    { "usuario": "victif", "puntos": 2 }
  ]
}
```

Haz commit y en ~30 segundos la tabla se actualiza para todos.

### Agregar un jugador nuevo
Agrega una línea dentro del array `"jugadores"`:
```json
{ "usuario": "nuevojugador", "puntos": 0 }
```

Y agrega sus credenciales en `index.html` dentro del array `USUARIOS`:
```js
{ usuario: "nuevojugador", password: "sucontraseña" }
```

---

## 🚀 Cómo publicar en GitHub Pages

1. Sube todos los archivos a un repositorio de GitHub
2. Ve a **Settings → Pages**
3. En *Source*, selecciona **`main`** y carpeta **`/ (root)`**
4. Guarda — en unos segundos tendrás una URL tipo:
   `https://TU-USUARIO.github.io/NOMBRE-REPO/`

> ⚠️ **Importante:** GitHub Pages requiere que el repositorio sea **público** para el plan gratuito.

---

## 👥 Usuarios registrados

Los usuarios y contraseñas están en `index.html`, dentro del array `USUARIOS`. Edítalos directamente ahí.

---

## 📱 Flujo de predicción

1. Usuario inicia sesión
2. Ve los partidos disponibles y presiona **Predecir**
3. Ingresa su marcador estimado
4. Se abre WhatsApp con el mensaje listo para enviar al admin
5. El admin registra el resultado y actualiza `data.json` manualmente

---

## 🔑 Contraseña admin

La contraseña para el modo admin en la tabla está en `tabla.html`:
```js
const ADMIN_PASSWORD = 'slpt2020#';
```
Cámbiala por una de tu preferencia.
