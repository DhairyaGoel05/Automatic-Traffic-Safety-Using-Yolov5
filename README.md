# Automatic Traffic Safety using YOLOv5

This project is a Flask-based web application that uses the YOLOv5 model to detect license plates in images and live video streams. The system allows users to upload images for detection and also supports real-time detection via a connected camera.

## Features
- **Image Upload & Detection**: Users can upload an image, and the YOLOv5 model detects license plates.
- **Live Camera Detection**: Supports real-time license plate detection from a webcam.
- **Flask API**: Provides endpoints to interact with the model.
- **CORS Support**: Allows cross-origin requests for better flexibility.

## Installation
### Prerequisites
Ensure you have the following installed:
- Python 3.10+
- Flask
- YOLOv5 (Ultralytics)
- Required Python libraries

### Setup
1. **Clone the repository**:
   ```sh
   git clone https://github.com/DhairyaGoel05/Automatic-Traffic-Safety-Using-Yolov5.git
   cd Automatic-Traffic-Safety-Using-Yolov5
   ```
2. **Clone the YOLOv5 repository**:
   ```sh
   git clone https://github.com/ultralytics/yolov5.git
   ```
3. **Create and activate a virtual environment**:
   ```sh
   python -m venv traffic
   source traffic/bin/activate  # For Linux/macOS
   traffic\Scripts\activate    # For Windows
   ```
4. **Install dependencies**:
   ```sh
   pip install -r requirements.txt
   ```
5. **Download the YOLOv5 model weights**:
   - Place the `best.pt` file inside the `yolov5/` directory.
   
## Usage
### Running the Flask App
```sh
python app.py
```
The application will start on `http://localhost:80`.

### API Endpoints
#### 1. Home Page
- **Endpoint**: `/`
- **Method**: `GET`
- **Description**: Renders the web interface.

#### 2. Image Prediction
- **Endpoint**: `/predict`
- **Method**: `POST`
- **Request Payload**:
  ```json
  {
    "image": "<base64-encoded-image>"
  }
  ```
- **Response**:
  ```json
  {
    "image": "<base64-encoded-predicted-image>"
  }
  ```

#### 3. Live Camera Detection
- **Endpoint**: `/live`
- **Method**: `GET`
- **Description**: Starts real-time license plate detection using a webcam.

## File Structure
```
Automatic-Traffic-Safety-Using-Yolov5/
│── app.py               # Flask application
│── requirements.txt     # Required dependencies
│── templates/
│   └── index.html       # Frontend UI
│── yolov5/
│   ├── detect.py        # YOLOv5 detection script
│   ├── best.pt          # YOLOv5 model weights
│── utils/
│   ├── main_utils.py    # Image processing utilities
```

## Screenshot
Below is a screenshot of the application in action:

![image](https://github.com/user-attachments/assets/a327213b-65f1-4175-99e3-88da8dda4e14)


## Troubleshooting
1. **ModuleNotFoundError**: Ensure all dependencies are installed.
   ```sh
   pip install -r requirements.txt
   ```
2. **Port Already in Use**: Change the port in `app.py`:
   ```python
   app.run(host="0.0.0.0", port=5000)
   ```
3. **YOLOv5 Errors**: Ensure `best.pt` is correctly placed in the `yolov5/` directory.


