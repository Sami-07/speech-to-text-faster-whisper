# Speech-to-Text Project

This project provides two different implementations for speech-to-text conversion using the Faster Whisper model:

1. **Batch Transcription** (`index.py`): Transcribes an audio file and outputs the results with timestamps
2. **Real-time Transcription** (`realtime_transcribe.py`): Records audio from your microphone and transcribes it in real-time

## Features

- Uses Faster Whisper, an optimized implementation of OpenAI's Whisper model
- Supports both CPU and GPU processing
- Real-time transcription with microphone input
- Batch processing of audio files
- Timestamp-based transcription output
- Automatic language detection
- Saves transcription logs

## Prerequisites

- Python 3.x
- PyAudio (for real-time recording)
- Faster Whisper

## Installation

1. Clone this repository
2. Install the required dependencies:

```bash
pip install faster-whisper pyaudio
```

## Usage

### Batch Transcription

To transcribe an audio file:

1. Place your audio file (e.g., `sample.m4a`) in the project directory
2. Run the script:

```bash
python index.py
```

The script will output:
- Detected language and its probability
- Transcription with timestamps for each segment

### Real-time Transcription

To start real-time transcription from your microphone:

```bash
python realtime_transcribe.py
```

- The script will continuously record audio in 1-second chunks
- Each chunk will be transcribed and displayed in real-time
- Press Ctrl+C to stop recording
- The complete transcription will be saved to `log.txt`

## Configuration

### Model Settings

You can modify the model settings in both scripts:

- `model_size`: Choose from different model sizes (e.g., "large-v3", "medium.en")
- `device`: Set to "cpu" or "cuda" for GPU processing
- `compute_type`: Choose between "int8", "int8_float16", etc.

### Recording Settings

In `realtime_transcribe.py`, you can adjust:
- `chunk_length`: Length of audio chunks in seconds (default: 1)
- Audio format settings (channels, sample rate, etc.)

## Notes

- The real-time transcription uses a 16kHz sample rate and 16-bit PCM format
- Temporary WAV files are created and automatically cleaned up during real-time transcription
- The batch transcription supports various audio formats
- GPU processing requires CUDA-compatible hardware and appropriate drivers
