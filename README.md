---

# 🚀 IA-WebChat – Configuração no Google Colab  

Este projeto configura um ambiente no **Google Colab** para rodar **modelos de IA via Ollama**, utilizando o **Xterm** para um terminal interativo. A conversa com a IA acontece em uma **página web** acessada remotamente através da conexão criada com **Ngrok**.  

## ⚙️ Instalação  

### 1️⃣ **Configurar o Xterm**  
Instale o terminal interativo para executar comandos no Colab:  

```python
!pip install colab-xterm  
%load_ext colabxterm  
%xterm  
```

### 2️⃣ **Instalar e executar o Ollama**  
Baixe e instale o **Ollama**, deixando-o rodando em segundo plano:  

```bash
curl https://ollama.ai/install.sh | sh  
ollama serve &  
```

### 3️⃣ **Baixar e executar um modelo LLM**  
Escolha um modelo disponível no **Ollama** e execute-o. Exemplo:  

```bash
ollama run llama3.2:1b  
```

## 🌐 Conectar a IA via página web (Ngrok)  
Para acessar a IA remotamente, use **Ngrok** para expor o servidor Flask na web:  

```bash
!pip install pyngrok  
ngrok config add-authtoken <SEU_TOKEN_AQUI>  
```

Depois que o **Ngrok** iniciar, ele fornecerá um **link público**, que será a **página web** onde você poderá conversar com a IA.  

## 🛠️ Testar a conexão com IA  
Envie mensagens para o chatbot via **requisição POST**:  

```bash
curl -X POST -H "Content-Type: application/json" -d '{"message": "Olá"}' https://SEU_NGROK_URL/chat  
```

---
