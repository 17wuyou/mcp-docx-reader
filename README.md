# MCP Enabled DOCX Reader

Model Context Protocol (MCP) server exposes a tool called `read_docx` to read a single DOCX document. This has been tested on Claude Desktop and LibreChat with Ollama.

## Installation

### Prerequisites

- Python 3.8 or higher
- An MCP-enabled AI tool like Claude Desktop

### Installation Steps

1. Clone or download this repository
2. Install the package:
   ```bash
   pip install -e .
   ```

## Configuration

Add the following to your claude_desktop_config.json:

```json
{
    "mcpServers": {
        "mcp-docx-reader": {
            "command": "uvx",
            "args": [
                "--from",
                "git+https://github.com/17wuyou/mcp_docx_reader@main",
                "mcp_docx_reader"
            ]
        }
    }
}
```

## Usage

The server exposes a single tool `read_docx` that accepts a filename parameter. The DOCX file should be placed in a directory specified by the `DOCX_DIRECTORY` environment variable (default: "./docx").

Example usage:
```
read_docx(filename="example.docx")
```

## License

MIT