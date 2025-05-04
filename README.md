# PDF Exam Processor by Aditi Nautiyal

# Still in the works and not complete yet so there may some issues !!!

## Overview

The PDF Exam Processor is a comprehensive web-based application designed to automate the extraction and processing of examination content from PDF documents. Using advanced machine learning techniques powered by TensorFlow, this system intelligently identifies and parses exam components such as title, type, questions, and answer choices, presenting them in an interactive question-and-answer interface.

This system bridges document analysis with web interaction capabilities to create a seamless workflow for digitizing exam content without manual transcription. The architecture employs both JavaScript-based components for web integration and a C-based backend for intensive processing tasks.

## System Architecture

The PDF Exam Processor is structured as a multi-component system:

1. **Web Frontend (JavaScript/HTML/CSS)**
   - Interactive exam UI for users
   - PDF file upload and processing
   - Question navigation and answer selection interface
   - Real-time feedback mechanisms

2. **PDF Processing Engine (JavaScript + TensorFlow.js)**
   - PDF text extraction
   - Content classification and structure analysis
   - Metadata identification (exam title, type)
   - Question and answer choice segmentation

3. **Neural Network Model (TensorFlow)**
   - Bidirectional LSTM architecture for sequence classification
   - Trained on annotated exam document corpus
   - Multi-class categorization of document elements
   - Pre-trained model conversion for web deployment

4. **C Language Backend (Optional)**
   - High-performance PDF parsing using Poppler
   - TensorFlow C API integration for model inference
   - Optimized for processing large documents
   - Provides API endpoints for web service integration

## Technical Specifications

### Web Components

- **Framework**: Vanilla JavaScript with modular architecture
- **PDF Processing**: PDF.js for client-side PDF parsing
- **Machine Learning**: TensorFlow.js for in-browser inference
- **Styling**: Custom CSS with responsive design principles
- **Dependencies**: TensorFlow.js, PDF.js

### Machine Learning Model

- **Architecture**: Bidirectional LSTM with embedding layer
- **Input**: Text sequences tokenized and padded to fixed length
- **Output**: Multi-class classification (Title, Type, Question, Answer, Other)
- **Training Data**: Annotated exam documents with labeled components
- **Performance Metrics**: Precision, recall, and F1-score for each class

### C Backend (Optional)

- **Libraries**: TensorFlow C API, Poppler for PDF processing
- **Memory Management**: Optimized for large document processing
- **Data Structures**: Custom structures for exam representation
- **Integration**: RESTful API for web service communication

## Installation Instructions

### Web Application Deployment

1. Clone the repository:
   ```
   git clone https://github.com/yourusername/pdf-exam-processor.git
   cd pdf-exam-processor
   ```

2. Install dependencies:
   ```
   npm install
   ```

3. Build the application:
   ```
   npm run build
   ```

4. Deploy to your web server:
   ```
   npm run deploy
   ```

### Model Training (Optional)

1. Install Python dependencies:
   ```
   pip install tensorflow numpy scikit-learn tensorflowjs
   ```

2. Prepare training data in the specified format (see Documentation)

3. Run the model training script:
   ```
   python tf-model-creator.py
   ```

4. Convert the model to TensorFlow.js format:
   ```
   tensorflowjs_converter --input_format keras model/exam_parser_model.h5 model/
   ```

### C Backend Compilation (Optional)

1. Install required libraries:
   ```
   apt-get install libtensorflow-dev libpoppler-cpp-dev
   ```

2. Compile the C backend:
   ```
   gcc -o pdf_processor c-pdf-processor.c -ltensorflow -lpoppler-cpp -std=c99
   ```

## Usage Guide

### Web Interface

1. Access the application through a web browser (Boilerexams if possible)
2. Upload an exam PDF using the file selector
3. Wait for the processing to complete
4. Navigate through extracted questions using the interface
5. Select answers for each question
6. Submit the completed exam

### Performance Optimization

- **Client-side Processing**: Reduces server load by performing PDF parsing in the browser
- **Model Size Optimization**: Quantized TensorFlow.js model for faster loading
- **Lazy Loading**: Questions loaded on-demand for large exams
- **Memory Management**: Efficient handling of large PDF documents

### Accuracy Enhancements

- **Text Preprocessing**: Normalization and cleanup for better recognition
- **Context-Aware Recognition**: Uses surrounding text to improve classification
- **Confidence Scoring**: Provides certainty levels for extracted components
- **Fallback Mechanisms**: Pattern matching when ML confidence is low

### Security Considerations

- **Client-side Processing**: All document processing occurs locally
- **No Data Transmission**: PDF content does not leave the user's browser
- **Input Validation**: Proper sanitization of extracted content
- **Error Handling**: Graceful failure modes for malformed documents

## Limitations and Future Work

- Current implementation optimized for standard multiple-choice exams
- Future enhancements planned for:
  - Essay question support
  - Multi-column layout handling
  - Image-based question extraction
  - Integration with learning management systems


## Citation

If you use this software in your research, please cite:

``` 
GitHub repository. https://github.com/aditinautiyal/boilerexams

## Acknowledgments

- TensorFlow
- Boilerexams
- The open-source community for coding examples that made this project possible
