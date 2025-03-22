# 🤖 Claude AI Documentation Assistant 📚

<div align="center">

![Claude + MCP Integration](https://raw.githubusercontent.com/anthropics/logo/main/claude-badge.png)

*A powerful MCP server that supercharges Claude with documentation search capabilities*

[![Python 3.8+](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)

</div>

## ✨ Features

- 🔍 **Smart Documentation Search** - Search across multiple AI/ML library documentation
- 🧠 **Claude Integration** - Seamless connection with Claude's advanced reasoning capabilities
- 🌐 **Intelligent Web Search** - Leverages Serper API for targeted documentation lookup
- 💨 **Fast Response Times** - Optimized for quick retrieval and processing
- 🧩 **Extendable Architecture** - Easily add more documentation sources

## 📋 Prerequisites

- 🐍 Python 3.8 or higher
- 🔑 Claude Pro subscription
- 🔐 Serper API key ([Get one here](https://serper.dev))
- 💻 Claude Desktop application

## 🚀 Quick Start

### 1️⃣ Installation

```bash
# Clone the repository
git clone https://github.com/your-username/claude-docs-assistant.git
cd claude-docs-assistant

# Create a virtual environment (recommended)
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

### 2️⃣ Configuration

Create a `.env` file in the project root with your API keys:

```
SERPER_API_KEY=your_serper_api_key_here
```

### 3️⃣ Start the MCP Server

```bash
python main.py
```

You should see output indicating the server is running and waiting for Claude to connect.

### 4️⃣ Connect Claude Desktop App

1. 📱 Open the Claude Desktop App
2. ⚙️ Click on your profile icon and select "Settings"
3. 🧰 Navigate to the "Tools" section
4. ➕ Click "Add Tool"
5. 🔗 Select "Connect to a local tool"
6. 🖥️ Follow the prompts to connect to your running MCP server
7. ✅ Confirm the connection is successful

## 🎮 Using Your Claude Documentation Assistant

Once connected, you can start asking Claude questions that will trigger the documentation search. For example:

```
Could you explain how to use FAISS with LangChain? Please search the langchain documentation to help me.
```

Claude will automatically use your MCP server to:
1. 🔍 Search for relevant documentation
2. 📥 Retrieve the content
3. 🧠 Process and explain the information

## 🔧 Under the Hood

### 📄 Code Structure

```
claude-docs-assistant/
├── main.py           # MCP server implementation
├── requirements.txt  # Project dependencies
├── .env              # Environment variables (API keys)
└── README.md         # This documentation
```

### 🔌 Supported Libraries

The assistant currently supports searching documentation for:

- 🦜 **LangChain**: `python.langchain.com/docs`
- 🦙 **LlamaIndex**: `docs.llamaindex.ai/en/stable`
- 🧠 **OpenAI**: `platform.openai.com/docs`

### 🧩 How It Works

1. 📡 The MCP server exposes a `get_docs` tool to Claude
2. 🔍 When invoked, the tool searches for documentation using Serper API
3. 📚 Results are scraped for their content
4. 🔄 Content is returned to Claude for analysis and explanation

## 🛠️ Advanced Configuration

### Adding New Documentation Sources

Extend the `docs_urls` dictionary in `main.py`:

```python
docs_urls = {
    "langchain": "python.langchain.com/docs",
    "llama-index": "docs.llamaindex.ai/en/stable",
    "openai": "platform.openai.com/docs",
    "huggingface": "huggingface.co/docs",  # Add new documentation sources
    "tensorflow": "www.tensorflow.org/api_docs",
}
```

### Customizing Search Behavior

Modify the `search_web` function to adjust the number of results:

```python
payload = json.dumps({"q": query, "num": 5})  # Increase from default 2
```

## 🔍 Troubleshooting

### Common Issues

- **🚫 "Connection refused" error**: Ensure the MCP server is running before connecting Claude
- **⏱️ Timeout errors**: Check your internet connection or increase the timeout value
- **🔒 API key issues**: Verify your Serper API key is correct in the `.env` file

### Debugging Tips

Add more detailed logging by modifying the main.py file:

```python
import logging
logging.basicConfig(level=logging.DEBUG)
```

## 📈 Performance Optimization

- ⚡ For faster response times, consider caching frequently accessed documentation
- 🧠 Limit the amount of text returned to Claude to avoid token limitations
- 🌐 Use more specific queries to get more relevant documentation

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. 🍴 Fork the repository
2. 🌿 Create a feature branch (`git checkout -b feature/amazing-feature`)
3. 💾 Commit your changes (`git commit -m 'Add some amazing feature'`)
4. 📤 Push to the branch (`git push origin feature/amazing-feature`)
5. 🔍 Open a Pull Request

## 📜 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgements

- [Anthropic](https://www.anthropic.com/) for creating Claude
- [Serper.dev](https://serper.dev) for their search API
- All the open-source libraries that make this project possible

---

<div align="center">
  Made with ❤️ for Claude enthusiasts
</div>
