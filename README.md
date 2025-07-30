# arXiv Research MCP Project

A comprehensive research assistant system that combines Model Context Protocol (MCP) servers with Chainlit UI for interacting with arXiv papers using AI.

## 🏗️ Project Structure

```
├── arxiv-chainlit-app/          # Chainlit web interface
├── arxiv-mcp-server-clean/      # MCP server implementation
├── arxiv-chat-ui/               # Alternative chat interface
└── .kiro/                       # Kiro IDE configuration
```

## 🚀 Features

- **arXiv Paper Search**: Search and retrieve papers from arXiv
- **AI-Powered Analysis**: Analyze papers using Mistral AI
- **Interactive Chat**: Have conversations about papers with context awareness
- **Paper Comparison**: Compare multiple papers across different aspects
- **MCP Integration**: Use as a Model Context Protocol server
- **Web Interface**: User-friendly Chainlit interface

## 📋 Prerequisites

- Python 3.8+
- Mistral AI API key
- Git

## 🛠️ Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/18Madhu-Sagar/mcp-research.git
cd mcp-research
```

### 2. Set Up Environment Variables

Copy the template files and configure your API keys:

```bash
# For the main project
cp .env.template .env

# For the Chainlit app
cp arxiv-chainlit-app/.env.template arxiv-chainlit-app/.env

# For the MCP server
cp arxiv-mcp-server-clean/.env.template arxiv-mcp-server-clean/.env
```

Edit each `.env` file and replace `your_mistral_api_key_here` with your actual Mistral AI API key.

### 3. Install Dependencies

#### For Chainlit App:
```bash
cd arxiv-chainlit-app
pip install -r requirements.txt
```

#### For MCP Server:
```bash
cd arxiv-mcp-server-clean
pip install -r requirements.txt
```

### 4. Get Your Mistral AI API Key

1. Visit [Mistral AI Console](https://console.mistral.ai/)
2. Sign up or log in
3. Generate an API key
4. Add it to your `.env` files

## 🚀 Usage

### Running the Chainlit App

```bash
cd arxiv-chainlit-app
python -m chainlit run app.py
```

The app will be available at `http://localhost:8000`

### Using the MCP Server

The MCP server can be used with Kiro IDE or other MCP-compatible clients. Configure it in your MCP settings:

```json
{
  "mcpServers": {
    "arxiv-research": {
      "command": "python",
      "args": ["arxiv_mcp_server.py"],
      "env": {
        "MISTRAL_API_KEY": "your_mistral_api_key_here"
      },
      "disabled": false
    }
  }
}
```

## 📖 Available Commands

### Chainlit Interface:
- `/search <query>` - Search for papers on arXiv
- `/select <number>` - Select a paper from search results
- `/papers` - View selected papers
- `/analyze <paper_id>` - Get AI analysis of a specific paper
- Chat naturally to discuss selected papers

### MCP Server Tools:
- `search_papers` - Search arXiv papers
- `get_paper_details` - Get detailed information about a paper
- `analyze_paper` - AI-powered paper analysis
- `chat_about_papers` - Have conversations about papers

## 🔧 Configuration

### Kiro IDE Integration

The project includes Kiro IDE configuration files in `.kiro/settings/mcp.json`. Make sure to update the API key in these files as well.

### Environment Variables

- `MISTRAL_API_KEY`: Your Mistral AI API key (required)
- `MISTRAL_AGENT_ID`: Optional agent ID for specialized responses
- `LOG_LEVEL`: Logging level (INFO, DEBUG, WARNING, ERROR)

## 🛡️ Security

- Never commit API keys to version control
- Use the provided `.env.template` files
- The `.gitignore` file is configured to exclude sensitive files
- API keys are loaded from environment variables only

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Ensure no secrets are committed
5. Submit a pull request

## 📝 License

This project is open source. Please check the license file for details.

## 🐛 Troubleshooting

### Common Issues:

1. **API Key Not Found**: Make sure your `.env` file is properly configured
2. **Import Errors**: Install all dependencies using `pip install -r requirements.txt`
3. **Connection Issues**: Check your internet connection and API key validity
4. **Gzip Errors**: The app includes fixes for common HTTP compression issues

### Getting Help:

- Check the logs for detailed error messages
- Ensure all environment variables are set correctly
- Verify your Mistral AI API key is valid and has sufficient credits

## 🔄 Updates

This project is actively maintained. Check for updates regularly and follow the setup instructions for any new features.