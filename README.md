# MCP Server

A Model Context Protocol (MCP) server implementation that provides document management capabilities through a CLI interface powered by Claude AI.

## Overview

This project implements an MCP server that allows you to:
- Read and edit documents
- List available documents
- Format documents using Markdown
- Summarize document contents
- Interact with documents through a CLI chat interface powered by Claude AI

## Features

- **Document Management**: Read, edit, and manage various document types
- **MCP Protocol**: Implements the Model Context Protocol for AI tool integration
- **Claude AI Integration**: Uses Anthropic's Claude for intelligent document processing
- **CLI Interface**: Command-line chat interface for document interactions
- **Multiple Document Formats**: Support for various document types (MD, PDF, DOCX, TXT)

## Prerequisites

- Python 3.8+
- UV package manager (recommended) or pip
- Anthropic API key

## Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd mcp-server
```

2. Create and activate a virtual environment:
```bash
# Using UV (recommended)
uv venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate

# Or using standard Python
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
```

3. Install dependencies:
```bash
# Using UV
uv pip install -r requirements.txt

# Or using pip
pip install -r requirements.txt
```

4. Set up environment variables:
Create a `.env` file in the project root:
```env
CLAUDE_MODEL=claude-3-sonnet-20240229
ANTHROPIC_API_KEY=your_anthropic_api_key_here
USE_UV=1  # Set to 0 if not using UV
```

## Usage

### Basic Usage

Run the main application:
```bash
python main.py
```

Or with UV:
```bash
uv run main.py
```

### Running the MCP Server

The MCP server can be run independently:
```bash
python mcp_server.py
```

Or with UV:
```bash
uv run mcp_server.py
```

### CLI Chat Interface

The application provides a CLI chat interface where you can:
- Ask questions about documents
- Request document summaries
- Format documents
- Edit document contents

## Project Structure

```
mcp-server/
├── core/                   # Core application modules
│   ├── chat.py            # Chat functionality
│   ├── claude.py          # Claude AI service integration
│   ├── cli.py             # CLI application logic
│   ├── cli_chat.py        # CLI chat interface
│   └── tools.py           # Utility tools
├── mcp_server.py          # MCP server implementation
├── mcp_client.py          # MCP client implementation
├── main.py                # Main application entry point
└── README.md              # This file
```

## MCP Server Features

The MCP server provides the following tools and resources:

### Tools
- `read_document`: Read contents of a document
- `edit_document`: Edit document content by replacing text

### Resources
- `docs://documents`: List all available documents
- `docs://documents/{doc_id}`: Get specific document content

### Prompts
- `format`: Rewrite document in Markdown format
- `summarize`: Summarize document contents

## Available Documents

The server comes with sample documents:
- `deposition.md` - Testimony documentation
- `report.pdf` - Technical report
- `financials.docx` - Financial information
- `outlook.pdf` - Performance projections
- `plan.md` - Implementation plan
- `spec.txt` - Technical specifications

## Configuration

### Environment Variables

- `CLAUDE_MODEL`: The Claude model to use (default: claude-3-sonnet-20240229)
- `ANTHROPIC_API_KEY`: Your Anthropic API key
- `USE_UV`: Set to "1" to use UV, "0" to use standard Python

### UV vs Python

The application can use either UV or standard Python. Set `USE_UV=1` in your `.env` file to use UV, or `USE_UV=0` to use standard Python.

## Development

### Running Tests

```bash
# Using UV
uv run pytest

# Using Python
python -m pytest
```

### Code Style

The project follows Python best practices and uses type hints throughout.

## Troubleshooting

### Common Issues

1. **API Key Error**: Ensure your `ANTHROPIC_API_KEY` is set correctly in the `.env` file
2. **Model Error**: Verify the `CLAUDE_MODEL` is a valid model name
3. **UV Not Found**: Install UV or set `USE_UV=0` to use standard Python

### Debug Mode

The MCP server runs in DEBUG mode by default. Check the console output for detailed logging information.

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## License

[Add your license information here]

## Support

For issues and questions, please open an issue on the repository.
