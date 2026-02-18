# Offline_Hindi_Voice_Assistant
# 🗣️ Offline Hindi Voice Assistant on Raspberry Pi 4 Model B

## 📌 Project Overview

This project implements a fully offline Hindi Voice Assistant deployed on a Raspberry Pi platform.  
The system performs real-time speech recognition, command processing, and text-to-speech synthesis without using any cloud services.

The objective is to design a low-latency, privacy-preserving embedded speech pipeline suitable for edge deployment in low-resource environments.

## 👩‍💻 About the Author

**Deepasri M**  
Electronics Engineering (VLSI Design and Technology)
Areas of Interest: VLSI Design, FPGA Design, Hardware Acceleration, Signal Processing, Edge AI  

Focused on building performance-optimized, hardware-aware intelligent systems for real-time applications.

## 👥 Team

- Deepasri M – System Architecture, Embedded Integration, Audio Pipeline Design  
- Sowmyavalli S – Model Deployment, Optimization
- Sahana S -  Testing & Validation  

## 🎯 Problem Statement
Offline, Privacy-Preserving Hindi Voice Assistant on Raspberry Pi

## Objective
Develop a low-latency, privacy-preserving voice assistant on an Arm-based SBC (e.g., Raspberry Pi) that processes Hindi voice commands entirely offline. The assistant should handle local queries (time, weather, etc.) using on-device ASR and TTS.

## Project Description
Students will build an embedded speech pipeline performing:

  Speech-to-text using a lightweight ASR model (e.g., Coqui STT or fine-tuned wav2vec2 for Hindi).
  Command parsing and intent recognition in Python.
  Text-to-speech responses using local TTS (eSpeak-NG or Festival).
  End-to-end on the Raspberry Pi CPU with no cloud dependency.
  
## Key Requirements

# Hardware:
  Raspberry Pi 5 or 4 (or similar Arm SBC).
  USB microphone.
  Speaker via 3.5 mm jack or HDMI.
Where possible, aim to use the CPU without additional accelerators/hats. Solutions that are well-optimised through use of Quantisation, KleidiAI, and appropriate model selection - and therefore able to run entirely on CPU - are of great interest.

# Software:
  Python with PyAudio for audio I/O.
  Coqui STT or fine-tuned wav2vec2 for ASR, or similar.
  eSpeak-NG or Festival for TTS.
  Custom Python logic for intent recognition and command execution.

# Performance Targets
  Sub-2-second response time per command.
  Accurate recognition for 10–15 Hindi commands.
  Robust, fully offline operation.

# Deliverables
  Source code for the full voice assistant pipeline.
  Documentation of any model fine-tuning / optimization steps.
  Demo video showing responses to multiple commands.
  Short report on architecture, challenges in Hindi ASR/TTS, and performance metrics.

# Learning Outcomes
  Hands-on experience with embedded speech AI and offline ASR/TTS.
  Understanding challenges of regional language processing.
  Integrating ASR, simple NLP/intent logic, and TTS on a constrained platform.

## 🏗️ System Architecture

### 🔹 Hardware
- Raspberry Pi 4  
- USB Microphone  
- Speaker  

### 🔹 Software Stack
- Python 3.9  
- Vosk (Offline Speech Recognition Engine)  
- eSpeak (Text-to-Speech Engine)  
- ALSA / PulseAudio (Audio Interface)  
## ⚙️ Working Principle

1. Audio is captured through the microphone at 16kHz sampling rate.  
2. Speech is converted to text using the Vosk Hindi ASR model.  
3. Commands are processed locally using rule-based intent parsing.  
4. The system generates an appropriate response.  
5. eSpeak synthesizes and outputs the response through the speaker.  

All processing is executed locally on the Raspberry Pi without any internet connectivity.

## 🚀 Features

- Fully offline operation  
- Real-time Hindi speech recognition  
- Low-latency response  
- Lightweight and optimized for ARM architecture  
- Privacy-preserving design  
- No external API dependency  

## 📊 Performance Metrics

| Parameter | Value |
|------------|--------|
| Average Response Time | ~1–1.5 seconds |
| CPU Usage | ~45–60% |
| Memory Usage | ~300–400 MB |
| Sampling Rate | 16 kHz |

*Performance may vary depending on model size and hardware configuration.*

## 📂 Project Structure

offline-hindi-assistant/
│
├── assistant.py
├── readme.txt
├── requirements.txt
└── setup.sh

## 🔧 Installation & Setup
1️⃣ Clone Repository
git clone https://github.com/Deepa-0408/hindi_voice_assistant.git
cd offline-hindi-assistant

2️⃣ Install Dependencies
pip install -r requirements.txt

3️⃣ Download Hindi Vosk Model

Download the Hindi model from the official Vosk website and place it inside the (models/) directory.

# link
https://alphacephei.com/vosk/models/vosk-model-small-hi-0.22.zip

4️⃣ Run the Application
python assistant.py

## 🧠 Applications

1. Rural and low-connectivity environments

2. Privacy-sensitive institutional setups

3. Smart home embedded systems

4. Assistive technology for elderly users

5. Educational voice-based interfaces

## 🔮 Future Enhancements

1. Model quantization for lower memory footprint

2. FPGA-based speech acceleration

3. Wake-word detection integration

4. Multilingual support

5. Edge AI co-processor integration

## 📈 Technical Significance

This project demonstrates:

1. Real-time embedded AI implementation

2. Edge deployment of speech models

3. Resource-constrained system optimization

4. Practical application of signal processing and embedded programming

It bridges the gap between AI algorithms and hardware-aware deployment, making it suitable for both academic and industrial exploration.
