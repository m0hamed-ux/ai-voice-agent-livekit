# Jarvis - AI Personal Assistant

A sophisticated AI-powered personal assistant inspired by Iron Man's Jarvis, built with LiveKit and Google's Gemini 2.5 Flash model. This real-time voice assistant can help you with weather information, web searches, and general assistance with a touch of personality.

## Features

- 🎤 **Real-time Voice Interaction** - Natural conversation with voice input/output
- 🌤️ **Weather Information** - Get current weather for any city
- 🔍 **Web Search** - DuckDuckGo integration for web searches
- 🎭 **Personality** - Sophisticated, slightly sarcastic AI persona
- 🔊 **Noise Cancellation** - Built-in noise cancellation for better audio quality
- 📱 **Video Support** - Video-enabled sessions
- 🌍 **Arabic Support** - Multilingual capabilities with Arabic instructions

## Prerequisites

- Python 3.8 or higher
- LiveKit account and API credentials
- Google AI Studio API key
- Internet connection for web search and weather features

## Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/m0hamed-ux/ai-voice-agent-livekit/
   cd ai-voice-agent-livekit
   ```

2. **Create a virtual environment**
   ```bash
   python -m venv venv
   
   # On Windows
   venv\Scripts\activate
   
   # On macOS/Linux
   source venv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up environment variables**
   
   Create a `.env` file in the root directory:
   ```env
   LIVEKIT_URL=your_livekit_url
   LIVEKIT_API_KEY=your_livekit_api_key
   LIVEKIT_API_SECRET=your_livekit_api_secret
   GOOGLE_API_KEY=your_google_ai_api_key
   ```

## Configuration

### Getting API Keys

1. **LiveKit Credentials**:
   - Sign up at [LiveKit](https://livekit.io/)
   - Create a new project
   - Get your URL, API Key, and API Secret

2. **Google AI Studio**:
   - Visit [Google AI Studio](https://makersuite.google.com/)
   - Create an API key for Gemini models

## Usage

### Running the Assistant

Start the Jarvis assistant:

```bash
python agent.py download-files && python agent.py start
```

The assistant will:
1. Initialize with noise cancellation
2. Connect to your LiveKit room
3. Greet you with: "Hi my name is Jarvis, your personal assistant, how may I help you?"

### Available Commands

- **Weather Queries**: "What's the weather in New York?"
- **Web Search**: "Search for the latest news about AI"
- **General Assistance**: Ask any question or request help

### Example Interactions

```
User: "Hello Jarvis, can you check the weather in Paris?"
Jarvis: "Of course sir, as you wish. Here's the current weather in Paris: 15°C, Cloudy"

User: "Search for recent developments in artificial intelligence"
Jarvis: "Right away, boss. I found several articles about recent AI breakthroughs..."
```

## Project Structure

```
Jarvis/
├── agent.py           # Main agent implementation
├── prompts.py         # AI personality and instructions
├── tools.py          # Weather and search tools
├── requirements.txt  # Python dependencies
├── .env             # Environment variables (create this)
├── .gitignore       # Git ignore rules
└── README.md        # This file
```

## Architecture

- **Agent Class**: [`Assistant`](agent.py) - Main AI agent using Google's Gemini 2.5 Flash Live Preview
- **Tools**: [`get_weather`](tools.py) and [`search_web`](tools.py) - External API integrations
- **Prompts**: [`AGENT_INSTRUCTION`](prompts.py) and [`SESSION_INSTRUCTION`](prompts.py) - AI personality configuration

## Customization

### Modifying Personality

Edit the [`AGENT_INSTRUCTION`](prompts.py) in [prompts.py](prompts.py) to change Jarvis's personality:

```python
AGENT_INSTRUCTION = """
# Personality
You are a personal assistant named Jarvis...
# Customize the personality here
"""
```

### Adding New Tools

Create new tools in [tools.py](tools.py):

```python
@function_tool()
async def your_custom_tool(
    context: RunContext,
    parameter: str) -> str:
    """
    Description of your tool.
    """
    # Implementation here
    return result
```

Then add it to the agent's tools list in [agent.py](agent.py).

## Troubleshooting

### Common Issues

1. **Connection Issues**:
   - Verify your LiveKit credentials
   - Check internet connection
   - Ensure firewall allows connections

2. **Audio Problems**:
   - Check microphone permissions
   - Verify audio device settings
   - Test noise cancellation settings

3. **API Errors**:
   - Confirm Google AI API key is valid
   - Check API quotas and limits
   - Verify environment variables are set

### Logs

The application logs important information. Check the console output for:
- Weather API responses
- Search results
- Error messages

## Dependencies

Key dependencies from [requirements.txt](requirements.txt):

- `livekit-agents` - Core LiveKit agent framework
- `livekit-plugins-google` - Google AI integration
- `livekit-plugins-openai` - OpenAI integrations
- `mem0ai` - Memory management
- `duckduckgo-search` - Web search functionality
- `requests` - HTTP requests for weather API

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## Developer

Created by **Mohamed EL KHAMLICHI**

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- Inspired by Tony Stark's Jarvis from Iron Man
- Built with LiveKit's real-time communication platform
- Powered by Google's Gemini AI model
- Weather data from wttr.in
- Web search via DuckDuckGo

---

*"Sometimes you gotta run before you can walk."* - Tony Stark
