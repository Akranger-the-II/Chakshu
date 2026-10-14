Markdown

# Chakshu 👁️🔊

**Voice-Controlled Real-Time Visual Assistant for the Visually Impaired**

Chakshu is an accessibility-first computer vision and voice-interactive system developed to help visually impaired individuals understand their immediate environment completely hands-free. By combining speech recognition, state-of-the-art vision-language models, and natural voice synthesis, Chakshu acts as an auditory guide to the physical world.

---

## Overview

Interacting with digital accessibility tools often requires screens, buttons, or physical interfaces that can be challenging to navigate. Chakshu eliminates physical control barriers entirely:

* **Spoken Inquiries**: Trigger actions using intuitive voice commands like `"Start"` or `"Describe"`.
* **Intelligent Scene Captioning**: Captures high-resolution video frames and infers detailed natural-language scene descriptions locally.
* **Auditory Feedback**: Vocalizes scene details through natural text-to-speech audio in real time.

---

## How It Works

                    [ Launch Application ]
                               │
                               ▼
               Auditory Cue: "Chakshu is ready"
                               │
                               ▼
                  [ Listening for Voice Command ]
                    /                         \
                   /                           \
           "Start" / "Describe"              "Quit" / "Exit"
                 /                               \
                ▼                                 ▼
     Speaks: "Analyzing scene..."          Speaks: "Goodbye"
                │                                 │
                ▼                            Application
      Captures Camera Frame                     Closes
                │
                ▼
      BLIP Model Captioning
                │
                ▼
       TTS Audio Readout
                │
                └───────────► Loops back to Listening

Code snippet


---

## Key Features

* **Hands-Free Operation**: Voice-driven pipeline powered by SpeechRecognition and PyAudio.
* **Deep Scene Understanding**: Employs the Salesforce BLIP (Bootstrapping Language-Image Pre-training) model for descriptive and context-aware image captioning.
* **Real-Time Visual Overlay**: Provides an on-screen video feed with visual status indicators and latest inference captions for sighted assistants, demonstrations, or debugging.
* **Hardware Friendly**: Capable of running inference locally on consumer-grade CPUs without requiring dedicated GPU acceleration.

---

## Project Structure

Chakshu/
├── Chakshu.py           # Main application engine and event loop
├── requirements.txt     # Python dependencies
├── LICENSE              # MIT License
└── README.md            # Project documentation


---

## Installation & Setup

### Prerequisites
* **Python**: `3.9` to `3.11`[cite: 3]
* **Microphone & Webcam**: Configured and set as system defaults
* **Internet Access**: Required for Google STT and gTTS voice synthesis[cite: 3]

### 1. Clone the Repository
```bash
git clone [https://github.com/Akranger-the-II/Chakshu.git](https://github.com/Akranger-the-II/Chakshu.git)
cd Chakshu
```[cite: 3]

### 2. Create and Activate Virtual Environment
```bash
# Windows
py -3.11 -m venv venv
venv\Scripts\activate

# macOS / Linux
python3 -m venv venv
source venv/bin/activate

3. Install Dependencies
Bash

pip install --upgrade pip
pip install -r requirements.txt

    Note on PyAudio: If your system encounters issues building pyaudio, install it via your OS package manager:

        macOS: brew install portaudio && pip install pyaudio

        [cite: 3]

        Linux (Debian/Ubuntu): sudo apt install portaudio19-dev && pip install pyaudio

        [cite: 3]

        Windows: pip install pyaudio

        [cite: 3]

Usage

Start the system with:
Bash

python Chakshu.py

    Wait for the initial audio announcement: "Chakshu is ready. The camera is on."

    Speak clearly into your microphone:

        "Start" (or "Describe", "Look", "Scan"): Takes a snapshot of the current view and reads the scene aloud[cite: 3].

        "Quit" (or "Exit", "Stop", "Close"): Safely releases the webcam and exits the program[cite: 3].

Tech Stack
Module	Component / Library	Purpose
Vision Input	OpenCV (cv2)	

Frame capture, window rendering, and visual display[cite: 3]
Vision AI	Hugging Face Transformers (BLIP-Large)	

Neural image-to-text scene captioning[cite: 3]
Speech Recognition	SpeechRecognition + pyaudio	

Captures microphone input and detects triggers[cite: 3]
Speech Synthesis	gTTS + pygame	

Generates and streams realistic spoken feedback[cite: 3]
Runtime Engine	PyTorch (torch, torchvision)	

Neural network inference framework[cite: 3]
Roadmap

    [ ] Add fully offline speech-to-text integration using OpenAI Whisper.

    [ ] Add spatial depth estimation to detect obstacle distances ("table 2 meters ahead").

    [ ] Implement multilingual speech output for localized voice assistance.

    [ ] Add continuous narration mode that triggers automatically on major scene shifts.

Author

Akshat Tiwari

    https://github.com/Akranger-the-II

    [cite: 3]

License

This project is licensed under the MIT License — see the LICENSE file for details[cite: 3, 5].