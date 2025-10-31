# Gen-AI Multi-Modal Flask Backend

This repository contains the Python Flask backend for a multi-modal web application. The application can generate text, create images, and translate text based on user input from a chat interface.

It leverages the Hugging Face Inference API for state-of-the-art text and image generation and uses the `deep-translator` library for language translation.

## ✨ Features

* **Multi-Modal Responses:**
    * **Text Generation:** Generates concise, bullet-point descriptions for any given prompt using `mistralai/Mistral-Nemo-Instruct-2407`.
    * **Image Generation:** Creates and displays an image from a text prompt using `black-forest-labs/FLUX.1-dev`.
    * **Translation:** Detects the language of a user's input and translates it into English.
* **Flask Backend:** A lightweight web server to handle API requests.
* **REST API:** Provides a central `/chat` endpoint to process all user requests.
* **HTML Formatting:** Text responses are formatted as clean HTML lists for easy rendering in a web frontend.
* **Base64 Image Encoding:** Generated images are converted to base64, allowing them to be directly embedded in an HTML `<img>` tag.

## 🛠️ Technologies Used

* **Backend:**
    * [Flask](https://flask.palletsprojects.com/en/3.0.x/)
    * [Requests](https://requests.readthedocs.io/en/latest/)
* **AI & ML Services:**
    * [Hugging Face Inference API](https://huggingface.co/inference-api)
    * [deep-translator](https://pypi.org/project/deep-translator/) (for Google Translate)
    * [langdetect](https://pypi.org/project/langdetect/)
* **Image Processing:**
    * [Pillow (PIL)](https://pillow.readthedocs.io/en/stable/)

---

## 🚀 Getting Started

Follow these instructions to get a copy of the project up and running on your local machine.

### 1. Prerequisites

* Python 3.8 or newer
* A Hugging Face Account and [API Token](https://huggingface.co/settings/tokens)

### 2. Installation

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/RamyaS1184/Gen-AI.git](https://github.com/RamyaS1184/Gen-AI.git)
    cd Gen-AI
    ```

2.  **Create and activate a virtual environment:**
    ```bash
    # Windows
    python -m venv venv
    .\venv\Scripts\activate
    
    # macOS/Linux
    python3 -m venv venv
    source venv/bin/activate
    ```

3.  **Create `requirements.txt`:**
    Create a file named `requirements.txt` in the root of your project and add the following lines:
    ```
    Flask
    requests
    deep-translator
    langdetect
    Pillow
    ```

4.  **Install the dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

### 3. Configuration

You **must** add your Hugging Face API token to the application.

Open your Python file (e.g., `app.py`) and find this line:

```python
# This is the line you need to change:
headers = {"Authorization": "Hugging Face Token"}
