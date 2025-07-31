# Real-Time Audio Intent Classification

A Python-based system that captures voice input in real-time, converts speech to text using OpenAI's Whisper model, and classifies user intent using advanced NLP techniques.

## 🚀 Features

- **Real-time Audio Capture**: Records audio with automatic silence detection
- **Speech-to-Text (STT)**: Uses OpenAI's Whisper model for accurate transcription
- **Intent Classification**: Employs few-shot learning with the Serj/intent-classifier model
- **Automatic Processing**: Complete pipeline from voice input to intent detection
- **Multiple Intent Categories**: Supports various intent types including shopping, technical support, billing, etc.

## 🎯 Supported Intent Categories

- **Shopping**: Product purchases and browsing
- **Bill Payment**: Payment-related queries
- **Technical Issue**: Technical support and troubleshooting
- **Customer Support**: General help and account assistance
- **Billing Issue**: Payment authorization and billing problems
- **Returns & Refunds**: Product returns and refund requests
- **Product Inquiry**: Product information and recommendations
- **Delivery/Order Tracking**: Shipping and order status
- **Order Modification**: Changes to existing orders
- **Subscription Inquiry**: Plan information and subscriptions

## 📋 Prerequisites

- Python 3.8 or higher
- macOS, Windows, or Linux
- Microphone for audio input
- Internet connection for downloading models

## 🛠️ Installation

1. **Clone or download the project:**
   ```bash
   cd "Real-Time Audio Intent Classification"
   ```

2. **Create a virtual environment (recommended):**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On macOS/Linux
   # or
   venv\Scripts\activate     # On Windows
   ```

3. **Install required packages:**
   ```bash
   pip install transformers torch torchaudio datasets pyaudio librosa soundfile sounddevice matplotlib
   ```

   > **Note**: If you encounter issues with the `wave` package showing MySQL-python dependency errors, simply exclude it from the installation as it's not needed for this project.

4. **Verify installation:**
   ```bash
   python -c "import sounddevice, librosa, transformers; print('All packages installed successfully!')"
   ```

## 🎵 Usage

### Running the Script

1. **Execute the main script:**
   ```bash
   python script.py
   ```

2. **Follow the prompts:**
   - The script will display "🎤 Listening... Speak now"
   - Speak clearly into your microphone
   - The recording will automatically stop after 2 seconds of silence
   - View the transcription and detected intent

### Using the Jupyter Notebook

1. **Start Jupyter:**
   ```bash
   jupyter notebook
   ```

2. **Open `audio-classifier-notebook.ipynb`**

3. **Run cells sequentially** to understand each step of the process

## 📁 Project Structure

```
Real-Time Audio Intent Classification/
├── README.md                           # This file
├── script.py                          # Main Python script
├── audio-classifier-notebook.ipynb     # Jupyter notebook with detailed explanations
├── Real-Time Audio Intent Classification.docx  # Project documentation
└── venv/                              # Virtual environment (if created)
```

## 🔧 Configuration

You can modify the following parameters in `scripts.py`:

```python
# Audio Settings
SAMPLE_RATE = 16000          # Sample rate for audio recording
SILENCE_THRESHOLD = 0.01     # Volume threshold for silence detection
SILENCE_DURATION = 2         # Seconds of silence before stopping recording
```

## 🧠 Models Used

1. **Speech-to-Text**: `openai/whisper-small`
   - Accurate multilingual speech recognition
   - Optimized for real-time processing

2. **Intent Classification**: `Serj/intent-classifier`
   - Sequence-to-sequence model for intent detection
   - Enhanced with few-shot learning examples

## 📊 Example Usage

```python
# Record and process audio
audio_data = record_audio_until_silence()
transcribed_text = transcribe_audio(audio_data)
detected_intent = classify_intent_few_shot(transcribed_text)

print(f"Transcription: {transcribed_text}")
print(f"Intent: {detected_intent}")
```

### Sample Outputs

**Input**: "I want to buy a new laptop for gaming"
- **Transcription**: "I want to buy a new laptop for gaming"
- **Intent**: "Shopping"

**Input**: "My internet keeps disconnecting every few minutes"
- **Transcription**: "My internet keeps disconnecting every few minutes"
- **Intent**: "Technical Issue"

## 🚨 Troubleshooting

### Common Issues

1. **ConfigParser Error**:
   - Remove `wave` from the package installation list
   - The built-in Python `wave` module is sufficient

2. **Microphone Not Detected**:
   ```bash
   # List available audio devices
   python -c "import sounddevice as sd; print(sd.query_devices())"
   ```

3. **Model Download Issues**:
   - Ensure stable internet connection
   - Models are downloaded automatically on first run

4. **Permission Errors**:
   - Grant microphone access to your terminal/IDE
   - On macOS: System Preferences > Security & Privacy > Microphone

### Performance Tips

- Use a good quality microphone for better accuracy
- Speak clearly and avoid background noise
- Ensure stable internet for initial model downloads
- Close unnecessary applications to free up memory

## 🤝 Contributing

Feel free to contribute to this project by:
- Adding new intent categories
- Improving audio processing
- Enhancing the user interface
- Optimizing model performance

## 🙏 Acknowledgments

- OpenAI for the Whisper speech recognition model
- Hugging Face for the transformers library and intent classification model
- The Python community for the excellent audio processing libraries

## 📞 Support

If you encounter any issues or have questions:
1. Check the troubleshooting section above
2. Review the Jupyter notebook for detailed explanations
3. Ensure all dependencies are properly installed

---

**Enjoy real-time voice intent classification! 🎤🤖**
