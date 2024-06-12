# MindMap Generator with Gemini 

This Flask application leverages the power of Google's Gemini API to automatically generate Mermaid diagrams from uploaded documents. It can handle PDFs, PPTX presentations, text files, and images, extracting key concepts and relationships to create visual representations.

## A Project Generated by Gemini LLM 🤯

This entire project, including this README, was generated by the Gemini LLM!  The goal was to create a barebones, minimum viable product (MVP) to explore the potential of AI-powered code generation. 

**Experiment Goal:** To understand how much effort is required for someone completely unfamiliar with:

- The Gemini API
- API usage in general
- The Flask web framework 

to create a basic working application.

**Next Steps:**  I plan to remake or significantly improve this app after learning more about the Flask framework, JavaScript, and other relevant libraries. This will allow for a direct comparison of the effort and time needed for both approaches: AI-assisted code generation vs. manual development. 

## Features

- **Document Upload:** Upload PDF, *PPTX, TXT, or *image files.
- **Gemini-Powered Analysis:**  Uses the Gemini API to analyze the content of uploaded documents and extract key concepts. 
- **Mermaid Diagram Generation:** Generates Mermaid code for mindmap diagrams based on the extracted concepts.
- **Image Rendering:** Uses `mermaid.ink` to convert the Mermaid code into PNG images.
- **Diagram Display:**  Displays the generated Mermaid diagrams to the user within the Flask app.

## Prerequisites

- **Python 3.7+**
- **Flask:**  `pip install Flask`
- **Google Generative AI Library:** `pip install google-generativeai`
- **PyPDF2:** `pip install PyPDF2`
- **python-pptx:** `pip install python-pptx`
- **Pillow (PIL):** `pip install Pillow`
- **requests:** `pip install requests`
- **Gemini API Key:**  You will need a valid API key from Google.  [https://developers.generativeai.google](https://developers.generativeai.google)

## Setup and Installation

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/your-username/mermaid-generator.git 
   cd mermaid-generator
   ```

2. **Install Dependencies:**
   ```bash
   pip install -r requirements.txt 
   ```

3. **Set API Key:**
   - Create a `.env` file in the project's root directory.
   - Add the following line to the `.env` file, replacing `YOUR_GEMINI_API_KEY` with your actual API key:

     ```
     API_KEY=YOUR_GEMINI_API_KEY
     ```

## Running the Application

1. **Run the Flask Development Server:**
   ```bash
   flask run
   ```

2. **Open in Browser:** Access the application in your web browser at `http://127.0.0.1:5000/`.

## Usage

1. **Upload a File:** Click on the "Choose File" button and select a supported document (PDF, PPTX, TXT, or image) from your computer.
2. **Generate Diagrams:** Click on the "Generate Diagrams" button.
3. **View and Download:** The app will display the generated Mermaid diagrams. You can download the images to your computer.

## Notes

- The accuracy of the generated Mermaid diagrams depends heavily on the quality of the input document and the ability of the Gemini API to extract relevant concepts.
- You can adjust the prompt in the `generate_mermaid_from_gemini()` function to customize the instructions for the Gemini API.
- For more complex use cases, consider exploring alternative methods for Mermaid diagram generation or more advanced text analysis techniques.

## Improvements and Future Work

This initial version of the Mermaid Diagram Generator provides a basic proof-of-concept. However, there are several areas where significant improvements can be made:

**1. Performance Optimization:**

- **Gemini API Calls:** The current implementation makes individual API calls for each page.  Batching API requests could significantly reduce processing time.
- **Asynchronous Processing:** Implementing asynchronous tasks (e.g., using Celery or Redis Queue) could improve responsiveness, especially for larger documents.
- **Caching:**  Caching frequently used data, such as Mermaid code or image responses from `mermaid.ink`, could further reduce processing and rendering time.

**2. User Interface (UI) Enhancements:**

- **Interactive Frontend:** Create a modern and user-friendly frontend using a JavaScript framework like React, Vue.js, or Angular. This would allow for:
    - Real-time feedback during file upload and processing.
    - User input for concept selection and diagram customization.
    - Interactive diagram exploration and manipulation. 

**3. Robust Error Handling:**

- **Mermaid Code Validation:** Implement more robust validation of the Mermaid code generated by Gemini, potentially using a Mermaid parser, to catch syntax errors before sending requests to `mermaid.ink`. 
- **Graceful Degradation:** Handle cases where the Gemini API fails to generate valid Mermaid code by providing informative error messages to the user or defaulting to a simple diagram. 

**4. Expanded File Format Support:**

- **PPTX and Image Handling:** Implement the logic to process PPTX presentations and images. This might involve:
    - Extracting text content from PPTX slides. 
    - Using OCR (Optical Character Recognition) for images.
- **Additional Formats:** Consider adding support for other document formats like DOCX (Word documents).

**5. Concurrency and Scalability:**

- **Testing with Multiple Users:** Conduct thorough testing with multiple users accessing the app concurrently to identify and address potential concurrency issues or bottlenecks. 
- **Deployment:** Deploy the app to a production-ready web server (e.g., Gunicorn, uWSGI) with a reverse proxy (e.g., Nginx) to handle multiple user requests efficiently. 

**6. Hosting and Accessibility:**

- **Cloud Hosting:** Explore cloud hosting platforms like AWS, Google Cloud, or Heroku to make the app accessible to others over the internet. 
- **User Authentication (Optional):** Implement user accounts to allow users to save and manage their generated diagrams.
 

## Contributing

Contributions are welcome! Please open an issue or submit a pull request if you have any suggestions, bug reports, or feature requests.