# AI Video Summarizer

![AI Video Summarizer](https://i.imgur.com/Jk1wxO3.png)

An interactive Streamlit app that summarizes YouTube videos, generates timestamp-based highlights, and downloads transcripts using AI.

## Overview

This project extracts YouTube captions or falls back to local Whisper transcription, then uses Google Gemini or OpenAI ChatGPT to:

- generate concise video summaries
- create timestamped highlights
- provide downloadable transcript and summary files

## Features

- YouTube URL input with caption retrieval via `youtube_transcript_api`
- Local Whisper fallback when transcripts are unavailable
- Support for Google Gemini and OpenAI ChatGPT models
- Clipboard copy and text download for summaries and transcripts
- Streamlit-based web interface with user-friendly model selection

## Prerequisites

- Python 3.10 or newer
- `pip` installed
- API credentials for one or both models:
  - `GOOGLE_GEMINI_API_KEY`
  - `OPENAI_CHATGPT_API_KEY`

## Installation

```bash
git clone https://github.com/24A31A05EH/AI-Video-Summarizer.git
cd AI-Video-Summarizer
pip install -r requirements.txt
```

## Configuration

Create a `.env` file in the project root with one or both of the following keys:

```env
GOOGLE_GEMINI_API_KEY="your-gemini-api-key"
OPENAI_CHATGPT_API_KEY="your-openai-api-key"
```

## Run the App

```bash
streamlit run app.py
```

Then open the provided local URL in your browser.

## Usage

1. Enter a valid YouTube video link.
2. Choose a model from the available options.
3. Select one of:
   - `AI Summary`
   - `AI Timestamps`
   - `Transcript`
4. Click the appropriate button to generate output.

## Project Structure

- `app.py` — Streamlit application entrypoint
- `whisper_transcriber.py` — local Whisper transcription fallback
- `src/` — helper modules for video info, prompts, timestamp formatting, and model calls
- `requirements.txt` — Python dependencies

## Notes

- If YouTube captions are unavailable, the app will attempt local transcription using Whisper.
- The app currently supports Gemini models `gemini-2.5-flash` and `gemini-2.0-flash-lite`.

## Contributing

Contributions, bug reports, and feature suggestions are welcome. Feel free to open an issue or submit a pull request.

## License

This project is licensed under the MIT License.
