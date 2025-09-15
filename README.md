# n8n AI Agent Workflow

This workflow automates the process of generating a full short video — from script to final MP4 — with the help of AI tools.

## Features

- **Scriptwriting**: Uses OpenRouter (Mistral-7B) to generate a 10-scene explainer script with caption, hashtags, and narration text.
- **Visual Extraction**: Pulls out the `Visuals:` lines from the script to use as prompts.
- **Image Generation**: Sends each scene description to Stability AI’s Stable Diffusion XL to create high-quality 1024×1024 images.
- **Voiceover**: Converts the narration text into speech with ElevenLabs and saves it as MP3.
- **Video Assembly**: Uses FFmpeg to merge all images with the narration into a single MP4 video.

## How to Use

1. Import `ai_agent_workflow.json` into your n8n instance.
2. Add your API keys:
   - **OpenRouter** (chat completions)
   - **Stability AI** (image generation)
   - **ElevenLabs** (text-to-speech)
3. Ensure FFmpeg is installed and available to n8n.
4. Run the workflow — it will:
   - Save scene images as PNGs  
   - Generate a voiceover MP3  
   - Output a final MP4 video at `/tmp/final_video.mp4`

## Requirements

- n8n (local or cloud)
- API keys for OpenRouter, Stability AI, and ElevenLabs
- FFmpeg installed on the machine running n8n

## Output

- 🎬 Ready-to-use MP4 explainer video  
- 🖼️ Scene-by-scene images  
- 🔊 Voiceover audio file  

---
