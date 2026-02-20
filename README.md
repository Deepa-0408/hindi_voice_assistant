# Offline_Hindi_Voice_Assistant
# 🗣️ Offline Hindi Voice Assistant on Raspberry Pi 4 Model B

## 📌 Project Overview

This project implements a fully offline Hindi Voice Assistant deployed on a Raspberry Pi platform.  
The system performs real-time speech recognition, command processing, and text-to-speech synthesis without using any cloud services.

The objective is to design a low-latency, privacy-preserving embedded speech pipeline suitable for edge deployment in low-resource environments.

## 👥 Team

- Deepasri M  
- Sowmyavalli S 
- Sahana S 

B.E- ELECTRONICS ENGINEERING (VLSI DESIGN AND TECHNOLOGY) 

K.S.RANGASAMY COLLEGE OF TECHNOLOGY, TIRUCHENGODE

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

<img width="887" height="465" alt="image" src="https://github.com/user-attachments/assets/e81d940a-9b26-458f-9597-ecf2c84b99f5" />

### 🔹 Hardware
- Raspberry Pi 4  
- USB Microphone  
- Speaker  

### 🔹 Software Stack
- Python 3.9  
- Vosk (Offline Speech Recognition Engine)  
- eSpeak (Text-to-Speech Engine)  
- ALSA / PulseAudio (Audio Interface)

## Commands
1. System Update (Mandatory First Step)
- sudo apt update
- sudo apt upgrade -y
2. Install Required System Dependencies
These are required for audio processing and TTS:
- sudo apt install python3 python3-pip python3-dev -y
- sudo apt install portaudio19-dev -y
- sudo apt install espeak-ng -y
- sudo apt install unzip wget -y
3. Install Python Libraries
- pip3 install --upgrade pip
- pip3 install vosk
- pip3 install pyaudio
4. Download Hindi ASR Model
- mkdir -p ~/models
- cd ~/models

  wget https://alphacephei.com/vosk/models/vosk-model-small-hi-0.22.zip

  unzip vosk-model-small-hi-0.22.zip

##After extraction, verify:
- ls
##You should see:
- vosk-model-small-hi-0.22
5. Verify Microphone Detection
Check input device:
- arecord -l
Test recording:
- arecord -d 5 test.wav
- aplay test.wav
If audio plays back correctly, the microphone is configured.
6. Verify Speaker Output
- speaker-test -t wav
- Press Ctrl + C to stop.
7. Check Audio Profile (If Needed)
- pactl list cards
If required:
- pactl set-card-profile <card_name> output:stereo-fallback
8. Confirm eSpeak Hindi Voice
- espeak-ng -v hi "नमस्ते"
If you hear Hindi speech → TTS is working.
9. Navigate to Project Directory
- cd ~
Confirm your Python file exists:
- ls
Example:
- assistant.py
Final Command to Run
- python assistant.py

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

## Conclusion

This project successfully demonstrates the implementation of a fully offline Hindi Voice Assistant on a Raspberry Pi platform. The system performs real-time speech recognition, intent processing, and text-to-speech synthesis without relying on cloud services, ensuring privacy and low-latency responses.

Through this work, we showcased the feasibility of deploying resource-efficient AI applications on embedded hardware, bridging the gap between software algorithms and hardware-aware optimization. The modular architecture allows easy future enhancements, such as multilingual support, FPGA acceleration, and wake-word detection.

Overall, this project highlights the potential of offline, edge-based voice assistants for low-connectivity or privacy-sensitive environments, making it a practical and scalable solution for real-world applications.
