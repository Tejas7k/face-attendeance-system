# Face Recognition Attendance System

This project is a Python-based Face Recognition Attendance System that allows for registering users, capturing their face data, and recording attendance based on facial recognition. The system is implemented using Flask for the web interface, OpenCV for face detection, and scikit-learn for face recognition using the K-Nearest Neighbors (KNN) algorithm.

---

## Features
- **User Registration**: Register new users by capturing their facial images via a webcam.
- **Face Detection**: Detects faces in real-time using the Haar Cascade Classifier.
- **Face Recognition**: Identifies registered users based on their facial data.
- **Attendance Logging**: Automatically logs attendance in a CSV file with the user's name, roll number, and timestamp.
- **Model Training**: Trains a KNN model with the captured facial data for face recognition.
- **Web Interface**: Provides an easy-to-use web interface for managing and viewing attendance.

---

## Requirements
- Python 3.8 or later
- OpenCV
- Flask
- scikit-learn
- pandas
- joblib

Install the required packages using the following command:
```bash
pip install opencv-python flask scikit-learn pandas joblib
```

---

## Directory Structure
```
.
|-- Attendance
|   |-- Attendance-{date}.csv  # Stores daily attendance records
|
|-- static
|   |-- face_recognition_model.pkl  # Serialized KNN model
|   |-- faces  # Contains folders of registered users' face images
|
|-- templates
|   |-- home.html  # Web interface HTML file
|
|-- haarcascade_frontalface_default.xml  # Haar Cascade for face detection
|-- background.png  # Background image for webcam feed display
```

---

## How to Run
1. Clone this repository and navigate to the project folder.
2. Ensure the required Python packages are installed.
3. Run the application using the command:
   ```bash
   python app.py
   ```
4. Open your web browser and navigate to `http://127.0.0.1:5000/` to access the web interface.

---

## Usage
### 1. Register a New User
- Go to the `/add` endpoint in the web interface.
- Enter the user's name and roll number.
- Capture facial images using the webcam.
- The system will automatically train the model with the new data.

### 2. Start Attendance
- Go to the `/start` endpoint in the web interface.
- The webcam feed will display. When a registered face is recognized, the user's attendance is logged.

### 3. View Attendance
- The main page (`/`) shows the attendance records for the current date.

---

## Key Functions
### 1. **Face Detection**
- Uses the `haarcascade_frontalface_default.xml` file to detect faces in images or webcam frames.

### 2. **Model Training**
- Captured face images are resized to 50x50 pixels and flattened.
- A KNN model is trained on the face data and saved as `face_recognition_model.pkl`.

### 3. **Attendance Logging**
- Attendance is logged in a CSV file named `Attendance-{date}.csv`.
- Records include `Name`, `Roll`, and `Time`.

---

## Dependencies
- **OpenCV**: For face detection and webcam integration.
- **Flask**: To create the web interface.
- **scikit-learn**: For training and using the KNN model.
- **pandas**: To handle CSV files for attendance.
- **joblib**: To save and load the trained model.

---

## File Descriptions
- `app.py`: Main application file that handles routes, face detection, and recognition.
- `haarcascade_frontalface_default.xml`: Pre-trained model for face detection.
- `background.png`: Background image for the webcam interface.
- `home.html`: HTML template for the web interface.

---

## Notes
- Ensure the Haar Cascade file (`haarcascade_frontalface_default.xml`) is present in the project directory.
- The system requires a webcam for user registration and attendance.
- Attendance logs are stored in the `Attendance` directory, with each day's attendance saved in a separate file.

---

## Future Improvements
- Add support for multiple cameras.
- Implement a more robust face recognition algorithm.
- Add a user management interface for editing or deleting registered users.
- Integrate with a database for better data management.
- Enhance the UI for a better user experience.

---

## Disclaimer
This project is for educational purposes only. Ensure compliance with privacy laws and regulations when deploying in a real-world scenario.

---

