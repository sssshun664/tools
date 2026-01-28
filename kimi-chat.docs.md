# Kimi K2.5 Chat - Full Documentation

## Overview
This is a streamlined chat application leveraging the OpenRouter API to access MoonshotAI's Kimi K2.5 model. The tool provides a web interface for conversations with this powerful LLM, optimized for mobile access.

## About Kimi K2.5
MoonshotAI's Kimi K2.5 is a state-of-the-art language model with the following capabilities:
- **Context Length**: 262,144 tokens (extremely large context window)
- **Multimodal**: Supports text and image input
- **Reasoning**: Extended thinking capabilities for complex problems
- **Visual Coding**: Advanced visual understanding for code-related tasks

## Core Features

**API & Response Handling**
- Integration with OpenRouter API for accessing Kimi K2.5
- Real-time response delivery via streaming
- Token consumption tracking (prompt tokens + completion tokens)

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
4. Model name is pre-configured as `moonshotai/kimi-k2.5`
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
- **Model ID**: `moonshotai/kimi-k2.5`
- **API Endpoint**: https://openrouter.ai/api/v1/chat/completions

## Privacy Note

All data persists locally in your browser. API key and chat history remain client-side except for communication with OpenRouter servers. The MoonshotAI provider does not retain prompts for training purposes.

## Pricing

Using Kimi K2.5 through OpenRouter:
- Input: $0.60 per million tokens
- Output: $3.00 per million tokens

Token usage is displayed after each response to help monitor costs.

## Key Differences from Original openrouter-chat.html

1. **Purple Theme**: Uses purple (#7c3aed) instead of blue to distinguish from the original
2. **Model Default**: Pre-configured for `moonshotai/kimi-k2.5`
3. **Storage Keys**: Uses `kimi_` prefix to avoid conflicts with other chat tools
4. **Branding**: Titled "Kimi K2.5 Chat" for clarity

## Browser Compatibility

Works in all modern browsers that support:
- Fetch API
- LocalStorage
- TextDecoder
- Streams API

## Limitations

- No file upload support (though the model supports multimodal input via API)
- No conversation export functionality
- Maximum context window is 262K tokens (extremely large, unlikely to be reached in normal use)
