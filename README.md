# DSP-Project
# Secure Communication using Voice Frequency Encoder and Decoder

## Introduction

This project is a secure communication system that utilizes a voice frequency encoder and decoder to transmit and receive messages. The encoder translates text into a series of audio frequencies, while the decoder converts these audio frequencies back into text. This system ensures that communication is carried out securely through voice frequencies, making it difficult for unintended listeners to decipher the message without the proper decoding mechanism.

## Technologies

The project is developed using Python and makes use of several libraries and tools to achieve its functionality:
- **Tkinter**: For building the graphical user interface (GUI).
- **Scipy**: For signal processing and handling audio data.
- **Numpy**: For numerical computations.
- **Pyaudio**: For audio recording and playback.
- **Sounddevice**: For playing the encoded audio signal.
- **SpeechRecognition**: For converting recorded audio to text.
- **Pyttsx3**: For text-to-speech functionality.
- **Matplotlib**: For plotting the signal in time and frequency domains.

## Technical Specification

- **Sample Rate**: 8000 Hz
- **Character Duration**: 0.04 seconds
- **Number of Samples per Character**: 320
- **FFT Size**: 1024

### Frequency Ranges for Characters
Each character is represented by a unique set of three frequencies. For example:
- 'a': [100, 1100, 2500]
- 'b': [100, 1100, 3000]
- 'c': [100, 1100, 3500]
- and so on.

## Dependencies

Ensure you have the following Python libraries installed before running the project:
- scipy
- numpy
- tkinter
- pyaudio
- sounddevice
- SpeechRecognition
- pyttsx3
- matplotlib

You can install these dependencies using pip:
```bash
pip install scipy numpy tkinter pyaudio sounddevice SpeechRecognition pyttsx3 matplotlib
```

## Usage

### To Encode

1. Run the encoder script:
   ```bash
   python encoder.py
   ```
2. Enter the text you want to encode in the provided text box.
3. Use the "Record Audio and Encode" button to record audio and convert it to text.
4. Use the "Save the generated signal as (.wav)" button to save the encoded signal as a .wav file.
5. Use the "Play the generated signal" button to play the encoded signal and view its time and frequency domain plots.

### To Decode

1. Run the decoder script:
   ```bash
   python decoder.py
   ```
2. Upload the .wav file containing the encoded signal using the "Upload Audio File (.wav)" button.
3. Use the "Run Decoder" button to open the decoding options.
4. Choose between "Decode using Frequency" or "Decode using Filter" to decode the audio file.
5. The decoded text will be displayed in the text widget.
6. Use the "Play Decoded Text" button to listen to the decoded text using text-to-speech.

## Encoder Part

The encoder script (`encoder.py`) includes the following functionalities:

- **Recording Audio**: Captures audio input from the microphone.
- **Audio to Text Conversion**: Uses Google Speech Recognition to convert recorded audio to text.
- **Text to Signal Encoding**: Encodes the text into a series of frequencies.
- **Signal Saving**: Saves the encoded signal as a .wav file.
- **Signal Playback**: Plays the encoded signal and plots its time and frequency domains.

Key functions:
- `record_audio(duration, filename)`: Records audio for a specified duration and saves it as a .wav file.
- `audio_to_text(filename)`: Converts the recorded audio to text.
- `generate_character_signal(frequencies)`: Generates the signal for a given character based on its frequencies.
- `encode_string_to_signal(input_string)`: Encodes the entire input string into a signal.
- `save_generated_signal()`: Saves the generated signal as a .wav file.
- `play_generated_signal()`: Plays the generated signal and plots its time and frequency domains.

## Decoder Part

The decoder script (`decoder.py`) includes the following functionalities:

- **File Upload**: Allows users to upload a .wav file containing the encoded signal.
- **Frequency Analysis**: Analyzes the audio segments to detect the encoded frequencies.
- **Signal Decoding**: Converts the detected frequencies back to text.
- **Text-to-Speech**: Plays the decoded text using a text-to-speech engine.

Key functions:
- `upload_audio_file()`: Handles the upload of the audio file.
- `analyze_segment_with_filters(segment)`: Analyzes an audio segment using bandpass filters to detect frequencies.
- `decode_audio_file_with_filters(file_path)`: Decodes the audio file using filters.
- `analyze_segment_with_frequencies(segment)`: Analyzes an audio segment using FFT to detect frequencies.
- `decode_audio_file_with_frequencies(file_path)`: Decodes the audio file using frequency analysis.
- `play_decoded_text()`: Plays the decoded text using a text-to-speech engine.

## Project Creators
This project was created by Faizer, Imran, and Rifat.
