# OpenRouter Multi-Model Chat - Full Documentation

## Overview
This is a versatile chat application leveraging the OpenRouter API to access various LLM models. The tool provides a web interface for conversations with multiple AI models including Kimi K2.5, GLM-4.7 Flash, Gemini 2.0 Flash, GPT-4o, Claude, DeepSeek, and custom models.

## Supported Models (Presets)

| Model | Provider | Description |
|-------|----------|-------------|
| Kimi K2.5 | MoonshotAI | 262K context, multimodal, extended thinking |
| GLM-4.7 Flash | Z-AI | Fast inference with reasoning capabilities |
| Gemini 2.0 Flash | Google | Fast multimodal model |
| GPT-4o | OpenAI | OpenAI's flagship model |
| Claude Sonnet 4 | Anthropic | Advanced reasoning and coding |
| DeepSeek Chat V3 | DeepSeek | Open-source large language model |
| Custom | Any | Specify any OpenRouter-supported model |

## Core Features

**Multi-Model Support**
- Dropdown selection for popular models
- Custom model input for any OpenRouter-supported model
- Easy switching between models without clearing history

**API & Response Handling**
- Integration with OpenRouter API
- Real-time response delivery via streaming
- Token consumption tracking (prompt + completion + reasoning tokens)
- `stream_options.include_usage` enabled for accurate token reporting

**Customization & Persistence**
- Adjustable system prompts to shape AI behavior
- LocalStorage for API credentials, model selection, prompts, and conversation history
- Responsive mobile-first design
- Keyboard shortcuts: Enter to submit, Shift+Enter for line breaks

## Setup Instructions

**Initial Configuration**
1. Open `kimi-chat.html` in your browser
2. Access settings via the gear icon (⚙️)
3. Input your OpenRouter API Key (obtainable from https://openrouter.ai/keys)
4. Select a model from the dropdown or choose "カスタムモデル" for custom input
5. Configure system prompt (optional; defaults to helpful assistant persona in Japanese)

**Chat Operation**
- Type messages in the input field
- Submit via button or Enter key
- Responses stream in real-time with token metrics displayed
- Use Shift+Enter to add line breaks without sending

**Managing Conversations**
- All conversations are automatically saved to browser storage
- Use "会話履歴をクリア" (Clear Chat History) button to reset
- Settings persist across sessions

## Technical Architecture

- **Protocol**: OpenRouter REST API v1 with Server-Sent Events for streaming
- **Storage**: Browser-based LocalStorage only
- **Dependencies**: None (vanilla HTML/CSS/JavaScript)
- **API Endpoint**: https://openrouter.ai/api/v1/chat/completions
- **Stream Options**: `include_usage: true` for token tracking

## Token Display

Token information is displayed after each response:
- **Prompt tokens**: Input token count
- **Completion tokens**: Output token count
- **Total tokens**: Sum of prompt and completion
- **Reasoning tokens**: Shown when available (for models with reasoning capabilities)

Example: `トークン: 150 + 200 = 350 (推論: 50)`

## Privacy Note

All data persists locally in your browser. API key and chat history remain client-side except for communication with OpenRouter servers.

## Model Pricing

Pricing varies by model. Check https://openrouter.ai/models for current pricing. Token usage is displayed after each response to help monitor costs.

## Browser Compatibility

Works in all modern browsers that support:
- Fetch API
- LocalStorage
- TextDecoder
- Streams API

## Limitations

- No file upload support (though some models support multimodal input via API)
- No conversation export functionality
- Context window limits vary by model
