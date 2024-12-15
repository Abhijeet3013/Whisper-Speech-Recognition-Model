# Whisper Speech Recognition Model

Whisper is a **state-of-the-art automatic speech recognition (ASR) model** developed by OpenAI. It is designed to transcribe and translate spoken language with high accuracy, even in challenging conditions like noisy backgrounds or diverse accents. This repository provides instructions for installing and using Whisper through both command-line and Python APIs.

---

## **Features**
- **Speech-to-Text**: Converts spoken audio into text.
- **Multilingual Support**: Recognizes and transcribes speech in over 50 languages.
- **Translation**: Translates audio in one language into another.
- **Robust Performance**: Handles noisy environments, varied accents, and challenging audio conditions.
- **Scalable Models**: Supports multiple model sizes (tiny, base, small, medium, large) to balance speed and accuracy.

---

## **Installation**
To use Whisper, ensure you have Python and FFmpeg installed.

### **Step 1: Install Whisper**
```bash
pip install git+https://github.com/openai/whisper.git
```

### **Step 2: Install FFmpeg**
FFmpeg is required for audio preprocessing:
```bash
sudo apt update && sudo apt install ffmpeg
```

---

## **Usage**

### **Command-Line Interface (CLI)**
You can run Whisper directly from the terminal for quick transcriptions:

#### **Basic Transcription**
```bash
whisper "path/to/audio.mp3" --model medium
```
- Replace `path/to/audio.mp3` with the path to your audio file.
- Use the `--model` flag to specify the model size (`tiny`, `base`, `small`, `medium`, `large`).

#### **View Help Options**
```bash
whisper -h
```
This command displays all available options and usage instructions.

---

### **Python API**
Whisper can also be used programmatically in Python for advanced integrations.

#### **1. Import Whisper**
```python
import whisper
```

#### **2. Load a Model**
Choose a model size and load it:
```python
model = whisper.load_model("base")
```

#### **3. Transcribe Audio**
Process an audio file and extract its transcription:
```python
result = model.transcribe("path/to/audio.mp3", fp16=False)
print(result["text"])
```
- `fp16=False` ensures compatibility with devices that don’t support half-precision floating-point numbers.
- `result["text"]` contains the final transcription.

---

## **Colab Notebook**
You can also try out Whisper directly in your browser using Google Colab:
[Whisper Colab Notebook](https://colab.research.google.com/github/openai/whisper/blob/main/notebook.ipynb)

---

## **Model Sizes and Trade-offs**
Whisper offers models of varying sizes to balance accuracy and performance:

| Model  | Size  | Speed   | Accuracy  |
|--------|-------|---------|-----------|
| Tiny   | 39 MB | Fastest | Basic     |
| Base   | 74 MB | Fast    | Good      |
| Small  | 244 MB| Moderate| Better    |
| Medium | 769 MB| Slower  | Excellent |
| Large  | 1550 MB| Slowest | Best      |

---

## **Applications**
- **Transcribing Meetings, Lectures, and Interviews**
- **Building Voice-Controlled Applications**
- **Creating Multilingual Subtitles for Videos**
- **Analyzing Audio Data for Research**

---



