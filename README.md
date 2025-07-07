## 🎬 iboothme Creative – AI Description Generator
This AI-powered tool automatically generates YouTube-style video descriptions for marketing and brand videos, especially those with little or no usable speech. It mimics the unique descriptive style used by iboothme Creative, leveraging OpenRouter-compatible LLMs (like Mistral) and OpenAI Whisper for transcription.

## 🚀 Features
✅ Upload a video or provide a YouTube/Direct URL

🎙 Transcribes audio using OpenAI Whisper


🖼 Extracts keyframes for silent videos

✍️ Uses AI (via OpenRouter) to generate iboothme-style descriptions

🧠 Auto-detects whether to use transcription or image-based inference

📦 Clean temporary video files after processing

🔓 Works offline with uploaded files or online via video URLs

## 📥 Input
The interface supports two modes of input:

1. Upload Mode
Upload a .mp4 video file directl
Max size depends on system and browser limit

2. URL Mode
Paste a YouTube or direct video URL
Downloads and processes the video on the fly

## 📤 Output
The output is a YouTube-style video description, containing:

View metadata and hashtags (mocked)

iboothme's contact details and links

Title line with product name and subtitle

A brief product/experience description

Use cases, promotional text, and calls to action

Optional links and relevant hashtags

## 🛠️ Installation
Make sure you have Python 3.8+ and run the following:
```bash
pip install gradio openai yt_dlp ffmpeg-python requests
pip install git+https://github.com/openai/whisper.git
```
You also need:
✅ FFMPEG (Path manually set in code)
✅ OpenRouter API key (input securely at runtime)

## 🧠 Models Used
OpenAI Whisper: For audio transcription
Mistral-7B (OpenRouter): For script-style description generation
Fallback to image-to-text if audio is silent

## 🔐 API Keys
This app uses OpenRouter's GPT-compatible API.
You'll be prompted securely for your key:

``` python
api_key = getpass.getpass("🔒 Please enter your OpenRouter API key (input hidden): ")
You can get it from: https://openrouter.ai/
``` 
## 🖼️ Frame-Based Description Logic
If no speech is detected, the app:
Extracts one resized frame from the video
Converts it to base64 JPEG
Sends it to the LLM for visual scene interpretation

## 🧪 Run the App
```bash
python app.py
```
Or if you're using Jupyter/Colab, just run all cells.

## 🌍 Share Link
The interface launches with:

```python
interface.launch(share=True)
```
So you get a public Gradio link instantly.

## 📁 Temp File Management
All temp files are stored in E:/temp (set manually), and videos are deleted after processing to save space.
