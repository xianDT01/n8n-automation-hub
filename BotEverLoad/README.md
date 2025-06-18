# 🤖 BotEverLoad para n8n

Este flujo de trabajo para [n8n](https://n8n.io/) permite integrar un bot de Telegram que conversa con los usuarios y descarga música y vídeos desde múltiples plataformas. Utiliza inteligencia artificial (IA) a través de OpenRouter y se conecta con una app backend llamada **EverLoad**, desarrollada en Spring Boot.

---

## 🚀 Funcionalidades

- ✅ Interacción conversacional con IA (modelo Mixtral vía OpenRouter)
- 🎵 Descarga de canciones en MP3 desde YouTube mediante `/musica [nombre]`
- 🎬 Descarga de vídeos en MP4 desde YouTube mediante `/video [nombre]`
- 🐦 Descarga de vídeos desde Twitter/X mediante `/twitter [enlace]`
- 📸 Descarga de reels o publicaciones desde Instagram mediante `/instagram [enlace]`
- 📘 Descarga de vídeos desde Facebook mediante `/facebook [enlace]`
- 📎 Envío del archivo directamente al chat de Telegram como documento
- 🧠 Respuestas automáticas si el mensaje no incluye comandos (modo asistente)
- 📋 Menú desplegable de comandos dentro del bot con `setMyCommands`
- 🌍 IA que explica cómo usar el bot si el mensaje no es reconocido
- 🌐 Multiplataforma: integración con backend Spring Boot + Swagger + Angular

---

## 🧩 Requisitos

- [n8n](https://n8n.io/) 
- Cuenta y bot configurado en [Telegram](https://core.telegram.org/bots)
- Clave API de [OpenRouter](https://openrouter.ai/)
- Aplicación backend **EverLoad** en funcionamiento

🔗 Repositorio de EverLoad: [github.com/xianDT01/Everload](https://github.com/xianDT01/Everload)

---

## ⚙️ Configuración

1. **Clona este repositorio y abre n8n.**
2. **Importa el archivo `BotEverLoad.json`.**
3. **Credenciales necesarias en n8n**:
   - Crea una credencial de tipo **Telegram API** con el nombre `telegramApi`.
   - Añade tu clave API de OpenRouter en el nodo correspondiente:
     ```json
     "Authorization": "Bearer TU_API_KEY"
     ```
4. **Backend EverLoad**:
   - Asegúrate de que tu app EverLoad esté ejecutándose en:
     ```
     http://host.docker.internal:8080
     ```
   - Si usas otro host (por ejemplo, en nube o localhost), cambia las URLs en los nodos HTTP del flujo.

---

## 🗂 Comandos disponibles

| Comando             | Acción                                                      |
|---------------------|-------------------------------------------------------------|
| `/musica [nombre]`  | Descarga el audio en MP3 desde YouTube                      |
| `/video [nombre]`   | Descarga el vídeo en MP4 desde YouTube                      |
| `/twitter [enlace]` | Descarga un vídeo desde Twitter/X                           |
| `/instagram [url]`  | Descarga reels o publicaciones desde Instagram              |
| `/facebook [url]`   | Descarga vídeos públicos desde Facebook                     |

---

## 📌 Nota técnica

Si usas este flujo fuera de Docker o en producción, revisa y adapta las URLs `host.docker.internal` por IPs o dominios públicos según tu entorno.

---

Hecho por [@xianDT01](https://github.com/xianDT01)
