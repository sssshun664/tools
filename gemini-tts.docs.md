# Gemini TTS

Convert text to speech using Google's Gemini 3.1 Flash TTS Preview model via the Gemini API.

## Features

- **Single Speaker TTS**: Convert text to speech with one selected voice
- **Multi Speaker TTS**: Generate conversations with up to 2 distinct speakers
- **30 Voice Options**: Choose from a variety of voice styles (Bright, Upbeat, Firm, Breathy, etc.)
- **Controllable Speech**: Use natural language to guide style, accent, pace, and tone
- **Audio Tags**: Inline tags like `[whispers]`, `[laughs]`, `[excited]` for expressive control
- **WAV Download**: Download generated audio as a WAV file
- **In-Browser Playback**: Listen to results immediately in the browser
- **Mobile Optimized**: Responsive design for all devices

## Usage

### Single Speaker Mode (Default)
1. **Enter API Key**: Add your Google AI API key (stored in browser)
2. **Select Voice**: Choose from 30 prebuilt voices
3. **Enter Text**: Write the text to be spoken, optionally with style directions
4. **Generate**: Click "Generate Speech" to create the audio
5. **Listen & Download**: Play the audio or download as WAV

### Multi Speaker Mode
1. **Switch Mode**: Click "Multi Speaker" button
2. **Configure Speakers**: Set names and voices for up to 2 speakers
3. **Write Dialogue**: Format as `SpeakerName: dialogue text`
4. **Generate**: Click "Generate Speech" to create the audio

## Voice Options

| Voice | Style | Voice | Style | Voice | Style |
|---|---|---|---|---|---|
| Zephyr | Bright | Puck | Upbeat | Charon | Informative |
| Kore | Firm | Fenrir | Excitable | Leda | Youthful |
| Orus | Firm | Aoede | Breezy | Callirrhoe | Easy-going |
| Autonoe | Bright | Enceladus | Breathy | Iapetus | Clear |
| Umbriel | Easy-going | Algieba | Smooth | Despina | Smooth |
| Erinome | Clear | Algenib | Gravelly | Rasalgethi | Informative |
| Laomedeia | Upbeat | Achernar | Soft | Alnilam | Firm |
| Schedar | Even | Gacrux | Mature | Pulcherrima | Forward |
| Achird | Friendly | Zubenelgenubi | Casual | Vindemiatrix | Gentle |
| Sadachbia | Lively | Sadaltager | Knowledgeable | Sulafat | Warm |

## Prompt Tips

### Controlling Style
Use natural language to describe how the text should be spoken:
- `Say cheerfully: Have a wonderful day!`
- `Say in a spooky voice: Something wicked this way comes`
- `Read this as a news anchor: Today's top stories...`

### Using Audio Tags
Place tags inline in brackets to modify delivery:
- `[whispers] This is a secret`
- `[laughs] That's hilarious!`
- `[excited] I can't believe it!`
- `[sighs] Well, I guess so...`

Common audio tags: `[amazed]`, `[crying]`, `[curious]`, `[excited]`, `[sighs]`, `[gasp]`, `[giggles]`, `[laughs]`, `[mischievously]`, `[panicked]`, `[sarcastic]`, `[serious]`, `[shouting]`, `[tired]`, `[trembling]`, `[whispers]`

### Multi Speaker Example
```
Speaker1: How's it going today?
Speaker2: Not too bad, how about you?
Speaker1: [excited] I just got some great news!
```

### Advanced Prompting
Structure prompts like directing a voice performance:
```
# AUDIO PROFILE: Jaz R.
## "The Morning Hype"

### DIRECTOR'S NOTES
Style: Enthusiastic radio DJ with infectious energy
Pacing: Fast and bouncy, no dead air
Accent: London, Brixton

### TRANSCRIPT
[excitedly] Good morning! You're locked in and it is absolutely
popping off right now. Turn this up!
```

## Supported Languages

The model auto-detects language. Supported languages include: Arabic, Bangla, Chinese (Mandarin), Dutch, English, French, German, Hindi, Indonesian, Italian, Japanese, Korean, Polish, Portuguese, Romanian, Russian, Spanish, Tamil, Telugu, Thai, Turkish, Ukrainian, Vietnamese, and many more.

## Getting an API Key

1. Visit [Google AI Studio](https://aistudio.google.com/)
2. Sign in with your Google account
3. Navigate to API keys
4. Create a new API key
5. Copy and paste it into this tool

## Limitations

- Text-only input, audio-only output
- 32k token context window limit
- No streaming support (full audio generated at once)
- Multi-speaker mode supports up to 2 speakers
- Voice may occasionally not match prompt instructions exactly
- Small percentage of requests may return 500 errors (retry if this happens)

## Privacy & Security

- API key is stored locally in your browser (localStorage)
- Text is sent to Google's Gemini API for processing
- No data is stored on any server by this tool

## Technical Details

- **Model**: gemini-3.1-flash-tts-preview
- **API**: Google Generative Language API (v1beta)
- **Audio Format**: PCM 16-bit, 24kHz, mono (converted to WAV in-browser)
- **Browser Support**: Modern browsers with Web Audio and Fetch API
- **Mobile Support**: iOS Safari, Chrome Mobile, Firefox Mobile
