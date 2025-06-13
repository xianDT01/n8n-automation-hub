# 🤖 BotEverLoad para n8n

Este flujo de trabajo para [n8n](https://n8n.io/) permite integrar un bot de Telegram que conversa con los usuarios y descarga canciones desde YouTube. Utiliza inteligencia artificial a través de OpenRouter y requiere una app backend llamada **EverLoad** para realizar las búsquedas y descargas.

---

## 🚀 Funcionalidades

- Interacción conversacional con IA (modelo Mixtral vía OpenRouter)
- Descarga de canciones en MP3 desde YouTube
- Envío del archivo directamente al chat de Telegram
- Detección del comando `/descarga [nombre]` para distinguir entre conversación e instrucciones

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
   - Si usas otro host (por ejemplo, en nube), cambia las URLs en los nodos HTTP del flujo.

---

## 📌 Nota

Si usas este flujo en otro entorno que no sea Docker, revisa y ajusta las URLs (`host.docker.internal`) por IPs locales o dominios públicos según tu despliegue.

---

Hecho por [@xianDT01](https://github.com/xianDT01)
