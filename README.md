# 🎤 JajaJarry | 100% Self Coding

> **La red social que nadie pidió, pero todos merecíamos:** una base de datos para coleccionar, puntuar y venerar chistes malos.

![Estado del humor](https://img.shields.io/badge/Humor-Negro%20y%20cuestionable-black?style=for-the-badge)
![Tecnología](https://img.shields.io/badge/Stack-Firebase%20%2B%20Vanilla%20JS-yellow?style=for-the-badge)
![Calidad del chiste](https://img.shields.io/badge/Calidad-Deliberadamente%20dudosa-red?style=for-the-badge)

---

## 🧠 ¿Qué es esto?

**JajaJarry** es un proyecto hecho entre amigos para llevar un ranking de:

- quién cuenta los peores chistes,
- quién sobrevive al cringe,
- y quién termina con puntaje negativo por insistir.

Todo vive en una app web simple, rápida y con energía de “esto no debería funcionar tan bien”.

---

## ✨ Features

- 🔐 Registro/Login con email y contraseña (Firebase Auth)
- 🎭 Feed de chistes en tiempo real
- 👍👎 Sistema de votos por chiste (con comentario opcional)
- 🏆 Ranking global de usuarios por puntaje
- 📈 Gráficas de evolución de puntajes (Chart.js)
- 👤 Perfil por usuario con historial y sus chistes
- 🔎 Búsqueda rápida de usuarios para votar directo
- 🎖️ Rangos automáticos según puntuación (de **El Maestro** a **Rey del Cringe**)

---

## 🧱 Stack técnico

| Capa | Tecnología |
|---|---|
| Frontend | HTML + CSS + JavaScript (vanilla) |
| Auth | Firebase Authentication (Email/Password) |
| Base de datos | Cloud Firestore |
| Gráficas | Chart.js |
| Hosting sugerido | Firebase Hosting / GitHub Pages (solo frontend) |

---

## 🚀 Cómo levantarlo

1. Clona este repo.
2. Crea un proyecto en Firebase.
3. Activa:
   - **Authentication** → Email/Password
   - **Firestore Database**
4. En `index.html`, ubica `FIREBASE_CONFIG` y coloca tus valores.
5. Abre `index.html` en el navegador.

Sí: es así de directo.  
No: no hay build step.  
Sí: duele menos que tus chistes.

---

## 🗂️ Estructura del proyecto

```text
jajajarry/
├── index.html       # App completa (UI + lógica JS)
├── images/          # Recursos visuales (opcional)
└── js/              # Carpeta reservada para separar scripts a futuro
```

---

## 🧮 Modelo de datos (Firestore)

### `users/{uid}`

```js
{
  username: string,
  email: string,
  totalScore: number,
  scoreHistory: [{ t: number, s: number }],
  joinedAt: Timestamp
}
```

### `jokes/{jokeId}`

```js
{
  authorUid: string,
  authorUsername: string,
  text: string,
  score: number,
  voters: {
    [uid]: { value: 1 | -1, comment: string, votedAt: number }
  },
  createdAt: Timestamp
}
```

---

## 🏅 Sistema de rangos

| Puntaje | Rango |
|---|---|
| 100+ | 👑 El Maestro |
| 60+ | 🏆 Leyenda |
| 30+ | ⭐ Estrella |
| 15+ | 🎤 Comediante |
| 0+ | 😄 Graciosillo |
| -10+ | 😬 Aprendiz |
| < -10 | 💀 Rey del Cringe |

---

## ⚠️ Aviso importante

Este proyecto es **humorístico y sarcástico**.  
No apto para personas alérgicas al cringe, al mal timing, o a los juegos de palabras con final triste.

---

## 🤝 Créditos

Hecho con amistad, mucho tiempo libre y decisiones cuestionables por un grupo de gente que claramente debería estar haciendo otra cosa.

---

## 📜 Licencia

Usen, rompan, mejoren, donden, clonen y sigan difundiendo el mal chiste con responsabilidad.
