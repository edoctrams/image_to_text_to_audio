#  Image to Text to Audio 🔊

This project extracts text from an image using **Tesseract OCR**, then converts that text to speech using **Google Text-to-Speech (gTTS)**. It's simple, beginner-friendly, and runs in a Python script or Jupyter Notebook.

---

##  Features

- 📤 Reads an image file (`.jpg`, `.png`, etc.)
- 🧠 Extracts readable text using OCR
- 🔊 Converts extracted text to an MP3 audio file
- Supports multiple languages (default: English)

---

##  How It Works

1. Open an image using `PIL.Image`
2. Extract text using `pytesseract.image_to_string()`
3. Convert text to speech using `gTTS`
4. Save the audio as `output_audio.mp3`

---

## ▶ How to Run

1. Make sure the image file (e.g. `quote.jpg`) is in the project folder
2. Run this Python code:

```python
import pytesseract
from PIL import Image
from gtts import gTTS

image = Image.open("quote.jpg")
extracted_text = pytesseract.image_to_string(image)
print(extracted_text)

tts = gTTS(text=extracted_text, lang='en')
tts.save("output_audio.mp3")
print("Audio saved as output_audio.mp3")
