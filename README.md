# voice_clone

A voice cloning model that can generate a synthetic voice that sounds like a specific person. The model
should be able to generate speech from text input, and it should be able to reproduce the unique vocal
characteristics of the target speaker.

# Skills
Python, Google Collab

# Tortoise TTS

This repository contains the source code for Tortoise TTS, a Text-to-Speech (TTS) system built using Python.

## Installation

To install Tortoise TTS and its dependencies, run the following commands:

pip3 install -U scipy
pip3 install -r requirements.txt
pip3 install transformers==4.19.0 einops==0.5.0 rotary_embedding_torch==0.1.5 unidecode==1.3.5
python3 setup.py install



# Usage
To use the voice clone model, follow these steps:

1. Clone the repository:
  git clone https://github.com/jnordberg/tortoise-tts.git
  cd tortoise-tts

2. Set up the custom voice:
  - Add your custom voice files to the 'tortoise/voices/custom' folder
  - Load the custom voice using the following command

    from tortoise.utils.audio import load_voice
    voice_samples, conditioning_latents = load_voice("custom")

4. Generate speech:
  - Example code to generate speech
    from tortoise.api import TextToSpeech
    tts = TextToSpeech()
  
    text = "Hello World, I am Akansha Singh and this is a voice clone model built using Python!"
    preset = "high_quality"
  - can change accordingly  
    gen = tts.tts_with_preset(text, voice_samples=voice_samples, conditioning_latents=conditioning_latents, preset=preset)
    torchaudio.save('generated-custom.wav', gen.squeeze(0).cpu(), 24000)






