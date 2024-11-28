# Real-Time Visual-to-Audio Captioning for Visually Impaired Users

## Overview
This project aims to provide real-time visual-to-audio conversion, empowering visually impaired users by describing images through generated captions and synthesized audio. 
The system employs a Transformer-based image captioning model and integrates with a browser extension for seamless functionality. 
Captions are generated from images using a trained model and converted into audio using IBM Watson's Text-to-Speech (TTS) service.

## Project Structure

```
├── train.ipynb
│   - Jupyter Notebook for training the image captioning model and saving the vocabulary.
│
├── test_w_browser_extension.ipynb
│   - Jupyter Notebook for setting up a FastAPI server to interact with the browser extension.
│   - Integrates the trained model with a browser extension.
│
├── popup.js
│   - JavaScript file for the browser extension.
│
├── test.html
│   - HTML file containing sample images for testing the browser extension.
│
├── requirements.txt
│   - List of all required Python packages.
```

## Features

 - **Image Captioning:** Generates descriptive captions for images using a trained Transformer-based model.
 - **Audio Output:** Converts captions into audio using IBM Watson's Text-to-Speech service.
 - **Browser Extension Integration:** Captions and synthesized audio are available directly from browser interactions.
 - **FastAPI Backend:** Provides a scalable backend to handle requests from the browser extension.
 - **Sample Test Page:** Contains example images for testing the entire system.

## Technology Used

 - **Deep Learning:**
   
     - TensorFlow
     - EfficientNetB0 CNN
     - Transformer Architecture
  
 - **Dataset:**
   
     - Flick30K Dataset from [Kaggle](https://www.kaggle.com/datasets/hsankesara/flickr-image-dataset)
 
 - **Backend:**

    - FastAPI
    - Ngrok
 
 - **Text-to-Speech:**
   
    - IBM Watson TTS
 
 - **Frontend:**
 
    - HTML
    - JavaScript (Browser Extension)

 - **Tools:**
   
    - Jupyter Notebook
    - Python

## How to Use the Code

**Prerequisites**

1. Install the required Python packages:

    - ```pip install -r requirements.txt```

2. Obtain the following:

   - Ngrok token: Sign up at ngrok to get a personal token.
   - IBM Watson API key and service URL: Sign up at IBM Cloud.

**Steps**

1. Train the Model

   - Open ```train.ipynb``` and execute all cells to:
     
     - Train the image captioning model.
     - Save the trained model and vocabulary for inference.

2. Start the Backend Server
   
   - Open ```test_w_browser_extension.ipynb``` and:
     
     - Define all custom functions used in the model.
     - Load the saved model and vocabulary.
     - Set up the FastAPI server with a publicly accessible ngrok tunnel.
     - Copy the ngrok public URL (displayed in the notebook output) to the popup.js file of the browser extension.

4. Configure the Browser Extension

   - Replace the URL in the ```popup.js``` file with the ngrok public URL.

4. Run the Test HTML Page

   - Start a Python HTTP server in the directory containing test.html: ```python -m http.server 8000```
     
   - Open `test.html` in your browser.

5. Use the Browser Extension

   - Enable the browser extension.
   - Hover over or click on an image in the test HTML page.
   - You will:

     - See the generated caption in the browser console.
     - Hear the audio output of the caption in real-time.

## Notes

 - **IBM Watson Configuration:** Update the API key and service URL in the ```test_w_browser_extension.ipynb``` file.
 - **Ngrok Setup:** Ensure ngrok is installed and authenticated with your token.
 - **Browser Extension:** Add the extension in developer mode in your browser and include the modified ```popup.js```.

## Future Enhancements

 - Support for multilingual captions and audio.
 - Improved accuracy with larger and diverse datasets.
 - Advanced decoding strategies for better captions.

## Contributors

 - Md. Azmol Fuad
 - Mostafa Rafiur Wasib
 - Chowdhury Nafis Saleh
