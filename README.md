# 🌤️ MCP Weather Server

[![Python 3.12+](https://img.shields.io/badge/python-3.12+-blue.svg?logo=python&logoColor=white)](https://www.python.org/)
[![Model Context Protocol](https://img.shields.io/badge/MCP-Protocol-orange.svg)](https://modelcontextprotocol.io/)
[![Built with uv](https://img.shields.io/badge/package%20manager-uv-purple.svg)](https://github.com/astral-sh/uv)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A lightweight and fast **Model Context Protocol (MCP)** server built in Python that equips AI assistants (like **Claude Desktop**) with real-time weather information using [wttr.in](https://wttr.in).

---

## ✨ Features

- ⚡ **Real-time Weather**: Fetch instant temperature and weather updates for any location worldwide.
- 🔌 **Standard MCP Compliance**: Built with the official Python `mcp` SDK using standard `stdio` transport.
- 🚀 **Blazing Fast Setup**: Managed with `uv` for near-instant dependency management.
- 🤖 **Seamless Claude Integration**: Easily connectable with Claude Desktop or any MCP-compatible AI client.

---

## 🛠️ Tools Exposed

| Tool Name | Parameters | Description | Example Output |
| :--- | :--- | :--- | :--- |
| `get_weather` | `location` *(string)* | Retrieves current temperature for the specified city/location | `+28°C` |

---

## 📋 Prerequisites

- **Python**: Version `3.12` or newer
- **uv**: Fast Python package installer and resolver ([Installation Guide](https://docs.astral.sh/uv/getting-started/installation/))
- **Claude Desktop** (Optional, for Claude Desktop integration)

---

## 🚀 Quick Start

### 1. Clone the Repository

```bash
git clone https://github.com/g-adarshg098/MCP_SERVER.git
cd MCP_SERVER
```

### 2. Install Dependencies

Using `uv`:

```bash
uv sync
```

Or using standard `pip`:

```bash
python -m venv .venv
# On Windows:
.venv\Scripts\activate
# On macOS/Linux:
source .venv/bin/activate

pip install -e .
```

### 3. Test Running the Server

Run directly with `uv`:

```bash
uv run mcp-weather.py
```

---

## 🖥️ Claude Desktop Integration

To use this weather tool inside **Claude Desktop**, add the server configuration to your `claude_desktop_config.json`.

### Config File Location

- **Windows**: `%APPDATA%\Claude\claude_desktop_config.json`
- **macOS**: `~/Library/Application Support/Claude/claude_desktop_config.json`

### Configuration

Add the following to your `mcpServers` object:

#### Windows (with `uv`)
```json
{
  "mcpServers": {
    "weather": {
      "command": "uv",
      "args": [
        "--directory",
        "C:\\Users\\adars\\OneDrive\\ADARSHG\\GENAI_2\\MCP_Server",
        "run",
        "mcp-weather.py"
      ]
    }
  }
}
```

> **Note**: Make sure to update the absolute path to match your project's directory location on your machine.

#### macOS / Linux (with `uv`)
```json
{
  "mcpServers": {
    "weather": {
      "command": "uv",
      "args": [
        "--directory",
        "/path/to/MCP_Server",
        "run",
        "mcp-weather.py"
      ]
    }
  }
}
```

After modifying the configuration, **restart Claude Desktop**. You should see the 🔨 hammer icon indicating available tools, including `get_weather`!

---

## 📂 Project Structure

```text
MCP_SERVER/
├── src/
│   └── mcp_server/
│       └── __init__.py
├── mcp-weather.py       # Weather MCP server implementation
├── pyproject.toml       # Project metadata and dependencies
├── uv.lock              # Lockfile for reproducible builds
├── .env.example         # Template for environment variables
├── .gitignore           # Git ignore rules
└── README.md            # Project documentation
```

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the [issues page](https://github.com/g-adarshg098/MCP_SERVER/issues).

---

## 👤 Author

**Adarsh G**
- GitHub: [@g-adarshg098](https://github.com/g-adarshg098)
- Email: its.adarshg15@gmail.com

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
