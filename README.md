# Open WebUI 👋

![GitHub stars](https://img.shields.io/github/stars/open-webui/open-webui?style=social)
![GitHub forks](https://img.shields.io/github/forks/open-webui/open-webui?style=social)
![GitHub watchers](https://img.shields.io/github/watchers/open-webui/open-webui?style=social)
![GitHub repo size](https://img.shields.io/github/repo-size/open-webui/open-webui)
![GitHub language count](https://img.shields.io/github/languages/count/open-webui/open-webui)
![GitHub top language](https://img.shields.io/github/languages/top/open-webui/open-webui)
![GitHub last commit](https://img.shields.io/github/last-commit/open-webui/open-webui?color=red)
![Hits](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fgithub.com%2Fopen-webui%2Fopen-webui&count_bg=%2379C83D&title_bg=%23555555&icon=&icon_color=%23E7E7E7&title=hits&edge_flat=false)

**Open WebUI is a self-hosted, extensible AI interface designed for local or cloud environments.** It supports various LLM runners including Ollama and OpenAI-compatible APIs and includes a built-in inference engine for enhanced features such as RAG and model management.

![Demo](./demo.gif)

---

## 🔑 Key Features

- **One-Command Setup**: Deploy using Docker, Kubernetes, or Python. Supports :ollama and :cuda images.
- **Model Integrations**: Use models from OpenAI-compatible APIs, Ollama, or self-hosted providers.
- **User Groups and Permissions**: Define custom access levels and secure routes.
- **Mobile-Friendly UI**: Responsive interface with PWA support for mobile offline usage.
- **Markdown, LaTeX, Voice & Video**: Enrich interactions with advanced formatting and media.
- **Model Builder & Import**: Create, edit, and import models directly via the UI.
- **Python Function Tooling**: Add native functions that integrate with LLMs.
- **RAG & Web Search**: Integrate files or live web results into chat with `#` commands.
- **Web Browsing & URL Embedding**: Inject web content directly into conversations.
- **Image Generation**: Works with local (ComfyUI, AUTOMATIC1111) and external tools (e.g. DALL-E).
- **Multi-model Support**: Chat with different models in the same session.
- **RBAC Security**: Role-based access with admin-only rights for sensitive actions.
- **Multilingual UI**: Full i18n support. Community translations welcome.
- **Plugin Framework (Pipelines)**: Extend functionality with custom Python logic.
- **Frequent Updates**: Actively maintained with ongoing enhancements.

---

## 🚀 Installation

### Python (>= 3.11)

```bash
pip install open-webui
open-webui serve
```

Accessible at [http://localhost:8080](http://localhost:8080)

---

### Docker (recommended)

```bash
docker run -d -p 3000:8080 \
--add-host=host.docker.internal:host-gateway \
-v open-webui:/app/backend/data \
--name open-webui --restart always \
ghcr.io/open-webui/open-webui:main
```

> To use with GPU:
```bash
docker run -d -p 3000:8080 \
--gpus all \
--add-host=host.docker.internal:host-gateway \
-v open-webui:/app/backend/data \
--name open-webui --restart always \
ghcr.io/open-webui/open-webui:cuda
```

> To connect to Ollama hosted elsewhere:
```bash
docker run -d -p 3000:8080 \
-e OLLAMA_BASE_URL=https://your-server.com \
-v open-webui:/app/backend/data \
--name open-webui --restart always \
ghcr.io/open-webui/open-webui:main
```

---

### Using OpenAI API Only

```bash
docker run -d -p 3000:8080 \
-e OPENAI_API_KEY=your_key \
-v open-webui:/app/backend/data \
--name open-webui --restart always \
ghcr.io/open-webui/open-webui:main
```

---

### Bundled Ollama Support

**With GPU:**
```bash
docker run -d -p 3000:8080 \
--gpus=all \
-v ollama:/root/.ollama \
-v open-webui:/app/backend/data \
--name open-webui --restart always \
ghcr.io/open-webui/open-webui:ollama
```

**Without GPU:**
```bash
docker run -d -p 3000:8080 \
-v ollama:/root/.ollama \
-v open-webui:/app/backend/data \
--name open-webui --restart always \
ghcr.io/open-webui/open-webui:ollama
```

---

## 🧰 Other Methods

- Docker Compose
- Helm
- Kustomize
- Native manual setup

---

## 🛠 Troubleshooting

If the WebUI can't connect to Ollama locally:

```bash
docker run -d --network=host \
-v open-webui:/app/backend/data \
-e OLLAMA_BASE_URL=http://127.0.0.1:11434 \
--name open-webui --restart always \
ghcr.io/open-webui/open-webui:main
```

---

## 🔄 Keeping Docker Updated

Using [Watchtower](https://containrrr.dev/watchtower/):

```bash
docker run --rm \
--volume /var/run/docker.sock:/var/run/docker.sock \
containrrr/watchtower --run-once open-webui
```

---

## 🧪 Dev & Offline Mode

Try the latest dev image (unstable):

```bash
docker run -d -p 3000:8080 \
-v open-webui:/app/backend/data \
--name open-webui \
--add-host=host.docker.internal:host-gateway \
--restart always \
ghcr.io/open-webui/open-webui:dev
```

Offline flag for environments without internet:

```bash
export HF_HUB_OFFLINE=1
```

---

## 📄 License

Licensed under the [BSD-3-Clause License](LICENSE).

---

## 🙌 Support

Need help?  
Join the community or open an issue.

---

<div align="center">
Built with ❤️ by the open-source community.
</div>
