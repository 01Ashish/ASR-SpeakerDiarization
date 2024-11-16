# Automatic Speech Recognition (ASR) System with Diarization

This repository provides a Flask-based application for Automatic Speech Recognition (ASR) with speaker diarization, using deep learning models for accurate transcription and speaker identification. The solution is designed to process audio files, separate speakers, and output transcripts with punctuation restoration.

## Features
- **Transcription**: Transcribes audio files to text using a Whisper model.
- **Speaker Diarization**: Separates audio by speakers using NVIDIA's NeMo models.
- **Punctuation Restoration**: Adds punctuation to the transcripts for improved readability.
- **Flask API**: Provides a REST API for uploading and transcribing audio files.
- **Multilingual Support**: Capable of transcribing multiple languages.

  
## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Endpoints](#endpoints)
- [Configuration](#configuration)
- [Contributing](#contributing)
- [License](#license)

## Installation
### Prerequisites
Ensure you have the following installed:

- Python 3.7 or higher
- PyTorch (compatible version for your system)
- CUDA (for GPU support, optional)

### Setup
1. Clone this repository:
`git clone https://github.com/yourusername/your-repo-name.git
cd your-repo-name`

2. Create and activate a virtual environment:
`python3 -m venv venv /n
source venv/bin/activate`

3. Install dependencies:
`pip install -r requirements.txt `
Note: Make sure to have all the dependencies specified in `requirements.txt`.
Download any required pre-trained models (if applicable) or set up configuration files as per your requirements.


## Usage
### Running the Flask App
To start the application, run:
```
bash
Copy code
python app.py  ```
The app will be accessible at ` http://127.0.0.1:5000`.

### Using the API
1. Transcribe Audio
Endpoint: /transcribe
Method: POST
Description: Uploads an audio file for transcription and diarization.

Example Request:

bash
Copy code
curl -X POST -F "audio=@path/to/your/audiofile.mp3" http://127.0.0.1:5000/transcribe
Example Response:

json
Copy code
{
    "transcript": "Speaker 1: Hello world. Speaker 2: Welcome to the ASR system."
}
Project Structure
php
Copy code
├── app.py                      # Main Flask application
├── diarize.py                  # Diarization utility functions and configurations
├── templates
│   └── index.html              # HTML template for home page
├── static                      # Static files (if any)
├── requirements.txt            # Project dependencies
└── README.md                   # This README file
Configuration
Model Configuration: Modify create_config() function in diarize.py to change model parameters for speaker diarization.
Punctuation Restoration: The model used for punctuation restoration can be adjusted in transcribe().
Contributing
Contributions are welcome! Please open issues or submit pull requests with improvements, bug fixes, or suggestions.

License
This project is licensed under the MIT License.

