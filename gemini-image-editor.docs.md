# Gemini Image Editor

Edit and transform images using Google's Gemini 3 Pro Image Preview model via OpenRouter API.

## Features

- **Single & Multiple Image Upload**: Select one or up to 14 images from your iPhone or any device
- **AI-Powered Editing**: Use natural language to describe edits
- **Multi-turn Conversations**: Iteratively refine your images through conversation
- **Customizable Settings**: Control aspect ratio (10 options) and resolution (1K/2K/4K)
- **Side-by-side Preview**: Compare original and generated images
- **Conversation History**: Track your editing journey
- **Mobile Optimized**: Designed for iPhone and touch devices

## Upload Modes

### Single Image Mode (Default)
- Upload one image at a time
- Perfect for simple edits and transformations
- Generated image automatically becomes the base for the next edit
- Enables iterative refinement through conversation

### Multiple Images Mode (Up to 14 Images)
- Upload up to 14 reference images
- Combine elements from multiple images
- Maintain character consistency across images
- Create compositions from various sources
- Remove individual images with the × button

## Usage

### Basic Usage (Single Image)
1. **Enter API Key**: Add your OpenRouter API key (stored in browser)
2. **Keep Single Image Mode**: Default mode is already selected
3. **Upload Image**: Tap to select an image from your device
4. **Write Prompt**: Describe how you want to edit the image
   - Example: "Add a sunset background"
   - Example: "Change to watercolor style"
   - Example: "Remove the background and make it transparent"
5. **Configure Settings**: Choose aspect ratio and resolution
6. **Generate**: Tap the generate button to create your edited image
7. **Iterate**: Continue editing by entering new prompts (the generated image becomes the new base)

### Advanced Usage (Multiple Images)
1. **Switch to Multiple Images Mode**: Tap "Multiple Images (up to 14)" button
2. **Upload Images**: Select up to 14 images from your device
   - You can select multiple files at once
   - Add more images by tapping the upload button again
   - Remove unwanted images by tapping the × button
3. **Write Prompt**: Describe how to combine or use the images
   - Example: "Create a group photo with these people in an office setting"
   - Example: "Combine these objects into a single product photo"
   - Example: "Use the style from the first image and apply it to the scene in the second image"
4. **Generate**: Create your composite image

## Image Settings

### Aspect Ratios
- **1:1** - Square (1024×1024)
- **2:3** - Portrait (832×1248)
- **3:2** - Landscape (1248×832)
- **3:4** - Portrait (864×1184)
- **4:3** - Landscape (1184×864)
- **4:5** - Portrait (896×1152)
- **5:4** - Landscape (1152×896)
- **9:16** - Mobile Portrait (768×1344)
- **16:9** - Widescreen (1344×768) *Default*
- **21:9** - Ultra Wide (1536×672)

### Resolutions
- **1K** - Standard resolution (default)
- **2K** - Higher resolution (recommended)
- **4K** - Highest resolution (slower generation)

## Model Information

This tool uses `google/gemini-3-pro-image-preview` via OpenRouter, which supports:
- Text-to-image generation
- Image-to-image editing with text prompts
- Multi-turn conversational editing
- High-fidelity text rendering in images
- Multiple reference images (up to 14 images)
- Character consistency across generated images

## Getting an API Key

1. Visit [OpenRouter](https://openrouter.ai/)
2. Sign up for an account
3. Navigate to the API Keys section
4. Create a new API key
5. Copy and paste it into this tool

## Tips for Best Results

- **Be Specific**: Detailed prompts yield better results
  - Good: "Add a golden sunset with purple clouds behind the mountains"
  - Less good: "Make it prettier"

- **Iterative Editing**: Make changes step by step
  - First: "Change the background to a beach"
  - Then: "Add palm trees on the sides"
  - Finally: "Make it look like a vintage photograph"

- **Style Transfers**: Mention specific artistic styles
  - "Convert to oil painting style"
  - "Make it look like a Studio Ghibli animation"
  - "Transform into pixel art"

- **Object Manipulation**: Be clear about what to add/remove
  - "Add a red umbrella in the person's hand"
  - "Remove the car from the street"
  - "Change the shirt color to blue"

- **Multiple Images Mode**: Best practices for combining images
  - Character Consistency: "Create a group photo with these 5 people making funny faces"
  - Object Composition: "Combine these products into a single catalog photo on a white background"
  - Style Transfer: "Apply the artistic style of the first image to the scene in the second image"
  - Scene Assembly: "Create a realistic living room using furniture from these images"
  - Reference Mixing: "Use the color palette from image 1 and the composition from image 2"

## Limitations

- Requires internet connection
- API costs apply (check OpenRouter pricing)
- Generation time varies based on resolution (4K takes longer)
- Some complex edits may require multiple iterations

## Privacy & Security

- API key is stored locally in your browser
- Images are sent to OpenRouter/Google for processing
- No data is stored on any server by this tool
- Clear your conversation history to remove local records

## Troubleshooting

**"Please enter your OpenRouter API key"**
- Make sure you've pasted your API key in the API Key field

**"Please upload an image first"** (Single Mode)
- Select an image using the upload button

**"Please upload at least one image"** (Multiple Mode)
- Switch to Multiple Images mode
- Select one or more images (up to 14)

**"You can only add X more image(s). Maximum is 14 images."**
- You've reached or are close to the 14 image limit
- Remove some images by clicking the × button on unwanted images
- Or proceed with the current selection

**"Error: HTTP error! status: 401"**
- Your API key is invalid or expired
- Get a new key from OpenRouter

**"Error: HTTP error! status: 429"**
- You've exceeded your rate limit
- Wait a few minutes and try again

**Image generation is slow**
- Try using 2K instead of 4K resolution
- Check your internet connection
- The model may be under heavy load

## Technical Details

- **Model**: google/gemini-3-pro-image-preview
- **API Provider**: OpenRouter
- **Output Format**: Base64-encoded PNG images
- **Browser Support**: Modern browsers with FileReader API
- **Mobile Support**: iOS Safari, Chrome Mobile, Firefox Mobile
