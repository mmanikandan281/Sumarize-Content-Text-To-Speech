# Sumarize-Content-Text-To-Speech
It is a solution to process PDF documents by extracting their content, summarizing it with OpenAI's GPT-3.5 Turbo model, and converting the summary into an audio file using Google Text-to-Speech (gTTS).

# Text-to-Speech Summarization Project

This project provides an efficient way to process PDF documents by extracting their content, summarizing it using OpenAI's GPT-3.5 Turbo model, and converting the summary into an audio file with Google Text-to-Speech (gTTS). Built for ease of use within the Google Colab environment, the workflow automates text extraction, summarization, and audio playback, offering a quick solution for information retrieval and accessibility.

---

## Features

- **PDF Text Extraction**: Easily extract text content from uploaded PDF files.
- **Text Summarization**: Generate concise summaries using OpenAI's GPT-3.5 Turbo.
- **Text-to-Speech Conversion**: Convert text summaries to audio using gTTS.
- **Audio Playback**: Automatically generate and play audio files for the summarized text.

---

## Technologies Used

- **OpenAI GPT-3.5 Turbo**: For high-quality text summarization.
- **LangChain**: Handles text splitting and chain operations.
- **Google Text-to-Speech (gTTS)**: Converts text into speech audio.
- **Python Libraries**: 
  - `pdfx` for extracting text from PDFs.
  - `tiktoken` for text tokenization.
  - `IPython` for seamless audio playback.
  - Integration in the Google Colab environment.

---

## Installation

Follow these steps to set up and run the project:

1. **Clone the Repository**
   ```bash
   git clone <https://github.com/mmanikandan281/Sumarize-Content-Text-To-Speech.git>
   cd <https://github.com/mmanikandan281/Sumarize-Content-Text-To-Speech>
   ```

2. **Install Dependencies**
   Install the required Python libraries:
   ```bash
   pip install openai pdfx langchain tiktoken langchain-openai gtts ipython
   ```

3. **Set Up API Keys**
   - Obtain your OpenAI API key from [OpenAI](https://platform.openai.com/).
   - Use Google Colab's `userdata` module to securely input the key:
     ```python
     from google.colab import userdata
     OPENAI_API_KEY = userdata.get('secretName')
     ```

---

## Usage

1. **Upload a PDF File**
   Upload your PDF using the `files` module in Google Colab:
   ```python
   from google.colab import files
   uploaded = files.upload()
   ```

2. **Extract Text from the PDF**
   Use `pdfx` to extract text content:
   ```python
   import pdfx
   pdf = pdfx.PDFx("example1.pdf")
   pdf_content = pdf.get_text()
   ```

3. **Summarize the Text**
   Process and summarize the text:
   ```python
   summary = chain.invoke(docs)
   ```

4. **Convert Summary to Speech**
   Generate and play the audio file:
   ```python
   from gtts import gTTS
   tts = gTTS(text=summary_text, lang='en')
   tts.save('summary.mp3')
   from IPython.display import Audio
   Audio("summary.mp3", autoplay=True)
   ```

---

## Example Output

1. **Input**: A sample PDF (`example1.pdf`).
2. **Output**:
   - Summarized text displayed in Colab.
   - Audio file (`summary.mp3`) for text-to-speech playback.

---

## License

This project is licensed under the MIT License. See the LICENSE file for more information.

---

## Contact

For inquiries or feedback, reach out to:

- **Name**: [Manikandan M]
- **Email**: [mmanikandan281@gmail.com]

---

Enjoy using the Text-to-Speech Summarization Project!
