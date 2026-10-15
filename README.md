# AI YouTube Shorts Generator (Vemmba)

Drop in any long-form YouTube video and get back ranked, viral-ready 9:16 shorts — no per-clip credits, no watermarks, full control over the highlight algorithm. Uses GPT-class LLM highlight detection and Whisper transcription, then auto-crops vertically for TikTok, Reels, and Shorts.

> Fork of [SamurAIGPT/AI-Youtube-Shorts-Generator](https://github.com/SamurAIGPT/AI-Youtube-Shorts-Generator) (MIT License © Anil Chandra Naidu Matcha), maintained here by [Vemmba](https://github.com/Vemmba).

## Requirements

- Python 3.10+
- **API mode (default)**: a [MuAPI](https://muapi.ai) key
- **Local mode** (`--mode local`): `ffmpeg` on PATH plus an LLM key (`OPENAI_API_KEY` or `GEMINI_API_KEY`)

## Setup

```bash
git clone https://github.com/Vemmba/ShortsGenerator.git
cd ShortsGenerator
python3.10 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
# Only for --mode local:
pip install -r requirements-local.txt

# Create .env in the project root:
# API mode (default)
MUAPI_API_KEY=your_muapi_key_here
# Local mode (--mode local)
LLM_PROVIDER=openai
OPENAI_API_KEY=your_openai_key_here
```

## Usage

```bash
# API mode (default)
python main.py "https://www.youtube.com/watch?v=..." --num-clips 3 --aspect-ratio 9:16

# Local mode (ffmpeg + Whisper run on your machine)
python main.py "https://www.youtube.com/watch?v=..." --mode local
```

Useful flags: `--num-clips`, `--aspect-ratio`, `--format`, `--language`, `--output-json`.

## License

MIT — see [LICENSE](LICENSE). Original work © Anil Chandra Naidu Matcha.
