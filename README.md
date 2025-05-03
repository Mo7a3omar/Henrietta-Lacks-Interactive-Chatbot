# Henrietta Lacks Interactive Chatbot 🧬

## Overview

This project is a Streamlit web application featuring an interactive chatbot that embodies the persona of Henrietta Lacks. Users can ask questions using their voice, and the chatbot responds with synthesized speech, drawing upon a detailed knowledge base about Henrietta Lacks' life, the HeLa cells, and their impact on science and ethics. The application uses Google's Gemini model for response generation, Google Text-to-Speech (gTTS) for audio output, and the `speech_recognition` library for voice input.

## Features

*   **Interactive Persona Chat:** Engage in conversation with an AI representing Henrietta Lacks.
*   **Voice Input:** Ask questions using your microphone via speech-to-text.
*   **Voice Output:** Hear Henrietta's responses generated via text-to-speech (gTTS).
*   **Gemini Powered:** Utilizes Google's Gemini API (`gemini-1.5-flash`) for generating contextually relevant responses based on a detailed system prompt.
*   **Streamlit Interface:** Simple and interactive web UI built with Streamlit.
*   **Educational:** Provides information about Henrietta Lacks, HeLa cells, medical history, and associated ethical considerations in an engaging format.

## Requirements

*   Python 3.x
*   A working microphone connected to your computer.
*   Speakers or headphones for audio output.
*   A Google Gemini API Key. You can obtain one from [Google AI Studio](https://aistudio.google.com/) ([3], [6]).
*   Potentially system-level audio libraries like `portaudio` (often required by `PyAudio`, a dependency of `SpeechRecognition`). Installation varies by OS (e.g., `sudo apt-get install portaudio19-dev` on Debian/Ubuntu, `brew install portaudio` on macOS).

## Installation

1.  **Clone the repository (or save the code):**
    If this is in a repository:
    ```
    git clone <your-repository-url>
    cd <repository-directory>
    ```
    If you only have the script file, save it as `app.py` (or your preferred name) in a new directory and navigate into it.

2.  **Create a `requirements.txt` file** with the following content:
    ```
    streamlit
    SpeechRecognition
    google-generativeai
    gTTS
    python-dotenv
    PyAudio # Often needed by SpeechRecognition for microphone access
    ```

3.  **Create a virtual environment (recommended):**
    ```
    python -m venv venv
    # On Windows
    venv\Scripts\activate
    # On macOS/Linux
    source venv/bin/activate
    ```

4.  **Install the required libraries:**
    ```
    pip install -r requirements.txt
    ```

## Configuration

1.  **Create a `.env` file** in the project's root directory.
2.  **Add your Google Gemini API key** to the `.env` file:
    ```
    GEMINI_API_KEY=YOUR_ACTUAL_API_KEY
    ```
    Replace `YOUR_ACTUAL_API_KEY` with the key you obtained from Google AI Studio. The script automatically loads this key ([3], [4]).

## Usage

1.  **Run the Streamlit application:**
    ```
    streamlit run app.py
    ```
    (Replace `app.py` with the actual filename if you named it differently).

2.  **Interact with the chatbot:**
    *   The application will open in your web browser.
    *   Click the "🎤 Ask Henrietta" button.
    *   Your browser may ask for permission to access your microphone. **Allow** it.
    *   Speak your question clearly when prompted.
    *   Wait for the speech to be processed and for Henrietta's audio response to play. The text of the question and response will also appear on the screen.

## How it Works

1.  The user clicks the "Ask Henrietta" button.
2.  The `speech_recognition` library listens via the microphone and converts the speech to text.
3.  The recognized text is sent as a prompt to the Google Gemini API, along with a detailed system prompt establishing the Henrietta Lacks persona and knowledge base.
4.  Gemini generates a text response in the persona of Henrietta Lacks.
5.  The `gTTS` library converts the text response into an MP3 audio stream.
6.  Streamlit plays the audio response back to the user and displays the text interaction.

## Dependencies

*   [Streamlit](https://streamlit.io/)
*   [SpeechRecognition](https://pypi.org/project/SpeechRecognition/)
*   [google-generativeai](https://pypi.org/project/google-generativeai/)
*   [gTTS](https://pypi.org/project/gTTS/)
*   [python-dotenv](https://pypi.org/project/python-dotenv/)
*   [PyAudio](https://pypi.org/project/PyAudio/) (typically installed as a dependency of SpeechRecognition)

## License

(Specify your project's license here. If you haven't chosen one, MIT is a common choice for open-source projects. You should include a `LICENSE` file in your repository.)

Example:
This project is licensed under the MIT License - see the `LICENSE` file for details.
