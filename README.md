Live Facial Emotion Detection with Alert System
This project implements a real-time facial emotion recognition system designed specifically for the Google Colab environment. It features high-accuracy detection and a visual alert system for specific emotional states.
<img width="669" height="408" alt="image" src="https://github.com/user-attachments/assets/fa1e55cf-7de9-4956-b960-20bde808a64d" />

🚀 Features
Real-time Streaming: Uses a custom JavaScript-to-Python bridge to stream webcam data from the browser to the Colab backend.
High Accuracy: Utilizes the FER library with MTCNN (Multi-task Cascaded Convolutional Networks) for superior face detection compared to standard Haar Cascades.
Performance Optimized: Frame sampling logic (1:3 ratio) ensures smooth execution without browser lag.
Sadness Alert System: Triggers a visual red banner in the feed if 'sadness' is detected for a sustained period (10+ frames).
Graceful Cleanup: Automatically releases camera hardware and removes browser UI elements upon termination.
🛠️ Tech Stack
<img width="947" height="637" alt="image" src="https://github.com/user-attachments/assets/112fe55c-b4b9-422e-9961-d29c5277ccd6" />

Language: Python 3.x
Core Libraries: FER, OpenCV, NumPy
Environment: Google Colab (utilizing google.colab.output and eval_js)
📋 Prerequisites
To run this in Colab, you need to install the following:
<img width="590" height="502" alt="image" src="https://github.com/user-attachments/assets/1be3afcb-cdea-40a6-b3d4-e8d3d8409798" />

pip install fer opencv-python
🔧 How It Works
JavaScript Bridge: Since Colab cannot access local hardware directly via standard OpenCV commands, a JS script creates a video element and captures frames as Base64 strings.
Processing: Python decodes the Base64 strings, runs the FER detection model, and calculates the dominant emotion.
Feedback: The calculated coordinates and emotion labels are sent back to a JS canvas overlay to draw bounding boxes in real-time.
🚦 Usage
Open the notebook in Google Colab.
Run the initialization cells to install dependencies and load models.
Execute the camera cell and grant browser permissions for the webcam.
Press the Stop button in the cell to end the session and clean up resources.
⚖️ License
This project is open-source and available under the MIT License.
