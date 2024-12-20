# Text Summarizer API

This project is a text summarization API built using Express.js and integrates multiple text extraction methods for documents (PDF, DOCX, TXT). It uses the Hugging Face `distilbart-cnn-12-6` model for summarization and Azure's Text Analysis API for text processing.

## Features

- **Text Summarization**: Summarizes any input text using a pre-trained transformer model from Hugging Face (`distilbart-cnn-12-6`).
- **File Upload**: Upload PDF, DOCX, or TXT files, and extract their text content for summarization.
- **Supports Multiple File Types**: Extracts text from various file formats including PDF, DOCX, and TXT.
- **Error Handling**: Provides meaningful error messages for unsupported files or issues during text extraction.

## Technologies Used

- **Express.js**: Web framework for building APIs.
- **Hugging Face API**: For text summarization using the `distilbart-cnn-12-6` model.
- **Azure Text Analysis API** (optional): Azure’s AI service used for text analysis tasks.
- **Multer**: Middleware for handling file uploads.
- **pdf-extraction**: Extracts text from PDF files.
- **Mammoth.js**: Extracts text from DOCX files.
- **File System (fs)**: To read files from the server's storage.

## Installation

To run this project locally, follow these steps:

1. Clone the repository:

    ```bash
    git clone https://github.com/Safiul-Alam-Sarker/StudyGenie.git
    ```

2. Navigate to the project directory:

    ```bash
    cd StudyGenie
    ```

3. Install the required dependencies:

    ```bash
    npm install
    ```

4. Create a `.env` file and add your credentials for Azure and Hugging Face:

    ```
    ENDPOINT=<Your Azure Endpoint>
    LANGUAGE_API_KEY=<Your Azure Language API Key>
    HF_KEY=<Your Hugging Face API Key>
    PORT=3000
    ```

5. Start the server:

    ```bash
    npm start
    ```

6. The server will be running at `http://localhost:3000`.

## API Endpoints

### 1. **POST /text**

This endpoint takes raw text and returns a summarized version of it.

**Request:**

```json
{
  "text": "Your text to be summarized"
}
