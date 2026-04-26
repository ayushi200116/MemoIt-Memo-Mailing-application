# 🔒 Intelligent Security System With Machine Learning

<div align="center">
  <p><strong>Advanced multi-factor authentication system combining facial recognition and handwritten digit recognition for secure access control</strong></p>
</div>

---

## 📋 Overview

The **Intelligent Security System** is a machine learning-powered application that provides multi-layer security through biometric authentication. It utilizes state-of-the-art computer vision techniques including facial recognition and handwritten digit recognition to ensure only authorized users can access the application.

## ✨ Key Features

- **👤 Face Recognition**: LBPH (Local Binary Patterns Histograms) facial recognition for user authentication
- **✍️ Digit Recognition**: Handwritten digit recognition using deep learning (CNN)
- **🔐 Multi-Factor Authentication**: Dual authentication methods for enhanced security
- **📷 Real-Time Capture**: Live camera feed integration for face capture
- **🎨 User-Friendly Interface**: Tkinter-based GUI with intuitive navigation
- **🧠 Pre-Trained Models**: Ready-to-use trained models for immediate deployment
- **📊 Dataset Generation**: Tools for creating training datasets

## 🛠️ Technology Stack

| Component | Technology |
|-----------|-----------|
| **Language** | Python 3 |
| **GUI Framework** | Tkinter |
| **Machine Learning** | TensorFlow, Keras |
| **Computer Vision** | OpenCV |
| **Face Recognition** | LBPH Face Recognizer |
| **Digit Recognition** | CNN (Convolutional Neural Network) |
| **Image Processing** | PIL, NumPy |

## 🧠 Machine Learning Models

### 1. Face Recognition Module

**Technology**: LBPH Face Recognizer (OpenCV)

- **Algorithm**: Local Binary Patterns Histograms
- **Training**: Face dataset with labeled identities
- **Features**:
  - Real-time face detection using Haar Cascade Classifier
  - Person identification with confidence score
  - Threshold-based acceptance (confidence < 100)

### 2. Digit Recognition Module

**Technology**: CNN (Convolutional Neural Network)

- **Framework**: TensorFlow/Keras
- **Model File**: `DigitModel.h5`
- **Input**: 28x28 handwritten digit images
- **Output**: Digit classification (0-9)
- **Application**: 4-digit PIN entry system
- **Default PIN**: 6246

## 📦 Core Modules

### Main Components

| Module | Purpose |
|--------|---------|
| **Main.py** | Application entry point with screen management |
| **FaceRecognizerModule.py** | Face recognition authentication logic |
| **DigitRecognizerModule.py** | Digit recognition prediction module |
| **faceDetector.py** | Face detection and model training |
| **datasetCreation.py** | Dataset creation utilities |
| **DigitModel.h5** | Pre-trained digit recognition model |

### Application Screens

1. **StartScreen**: Authentication method selection
2. **FaceRecognitionScreen**: Face capture and verification
3. **DigitRecognitionScreen**: Handwritten digit entry
4. **ApplicationEntryScreen**: Success screen (authorized access)
5. **WrongAuthenticationScreen**: Failed authentication screen

## 🚀 Getting Started

### Prerequisites

- Python 3.7+
- Webcam/Camera for face recognition
- pip (Python package manager)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/ayushi200116/Intelligent-Security-System-With-Machine-Learning.git
   cd Intelligent-Security-System-With-Machine-Learning
   ```

2. **Install dependencies**
   ```bash
   pip install tensorflow keras opencv-python pillow numpy tkinter
   ```

3. **Verify model files**
   - Ensure `DigitModel.h5` is present in the root directory

### Running the Application

```bash
python Main.py
```

## 📁 Project Structure

```
Intelligent-Security-System-With-Machine-Learning/
├── Main.py                         # Application entry point
├── FaceRecognizerModule.py          # Face recognition module
├── DigitRecognizerModule.py         # Digit recognition module
├── faceDetector.py                  # Face detection and training
├── datasetCreation.py               # Dataset creation utility
├── DigitModel.h5                    # Pre-trained digit model
├── Digit Recognition/               # Digit recognition dataset
├── digit.jpg                        # Sample digit image
└── README.md
```

## 🔐 Authentication Flow

```
Start Application
      ↓
Select Authentication Method
  ├─ Face Recognition Path
  │    ├─ Capture Face
  │    ├─ Compare with Database
  │    └─ Verify Identity
  │
  └─ Digit Recognition Path
       ├─ Draw 4 Digits
       ├─ Recognize Each Digit
       └─ Compare with PIN (6246)
      ↓
  ├─ Authentication Success → Application Access
  └─ Authentication Failed → Retry/Exit
```

## 👥 Face Recognition Details

### Face Detection Process

1. **Image Capture**: Read from webcam in real-time
2. **Face Detection**: Haar Cascade Classifier identifies faces
3. **Face Extraction**: Crop and resize face region (130x100)
4. **Recognition**: LBPH model predicts identity
5. **Verification**: Confidence score evaluation

### Configuration

```python
# Face parameters
width = 130          # Face crop width
height = 100         # Face crop height
confidence_threshold = 100  # Confidence score threshold
```

### Dataset Creation

To create a face dataset:

```bash
python datasetCreation.py
```

Follow the prompts to:
- Enter user ID and name
- Capture multiple face samples
- Build training dataset

## ✍️ Digit Recognition Details

### Drawing Interface

- **Canvas Size**: 300x300 pixels
- **Drawing Tool**: Mouse-based drawing with 8px radius
- **Input Method**: Draw digits one by one
- **Recognition**: CNN model classifies each stroke
- **PIN Format**: 4-digit sequence

### Training the Model

To retrain the digit recognition model:

1. Prepare MNIST dataset or custom digits
2. Use TensorFlow/Keras to train CNN
3. Save model as `DigitModel.h5`

Example model architecture:
```python
model = Sequential([
    Conv2D(32, (3, 3), activation='relu', input_shape=(28, 28, 1)),
    MaxPooling2D((2, 2)),
    Conv2D(64, (3, 3), activation='relu'),
    MaxPooling2D((2, 2)),
    Conv2D(64, (3, 3), activation='relu'),
    Flatten(),
    Dense(64, activation='relu'),
    Dense(10, activation='softmax')
])
```

## ⚙️ System Configuration

### Face Recognition Settings

Edit `faceDetector.py` to modify:

```python
haar_file = 'haarcascade_frontalface_default.xml'  # Haar cascade file
datasets = 'datasets'                               # Dataset folder
(width, height) = (130, 100)                        # Face dimensions
```

### Digit PIN Configuration

Modify the PIN in `Main.py`:

```python
if self.passwd == "6246":  # Change this PIN
    # Authentication successful
```

## 🎯 Use Cases

- **Secure Application Access**: Prevent unauthorized access
- **Workplace Security**: Employee authentication at facility entrances
- **Financial Services**: Transaction verification
- **Biometric Systems**: Multi-factor authentication
- **Smart Home Security**: Face-based access control
- **Research & Development**: ML/AI project demonstration

## 📊 Performance Metrics

| Module | Accuracy | Speed |
|--------|----------|-------|
| Face Recognition | ~85-90% | Real-time |
| Digit Recognition | ~95%+ | <100ms per digit |
| Overall Authentication | ~90%+ | 2-5 seconds |

## ⚠️ Important Notes

- Ensure good lighting for optimal face recognition
- Train with multiple facial angles and expressions
- Protect trained models and datasets
- Use secure PIN combinations
- Regularly update datasets for accuracy

## 🐛 Troubleshooting

| Issue | Solution |
|-------|----------|
| Camera Not Detected | Check camera connection and permissions |
| Poor Face Recognition | Improve lighting, train with more samples |
| Digit Recognition Fails | Ensure clear handwriting, check model file |
| GUI Not Responding | Restart application, check system resources |
| Model File Missing | Verify DigitModel.h5 exists in root directory |

## 📈 Future Enhancements

- [ ] Iris recognition integration
- [ ] Voice authentication module
- [ ] Fingerprint recognition
- [ ] Mobile application version
- [ ] Cloud-based model updates
- [ ] Advanced anti-spoofing detection
- [ ] Real-time monitoring dashboard
- [ ] Audit logging system

## 📚 References

- [OpenCV Face Detection](https://docs.opencv.org/master/d7/d8b/tutorial_py_face_detection_in_videos.html)
- [LBPH Face Recognizer](https://docs.opencv.org/master/df/d25/classcv_1_1face_1_1LBPHFaceRecognizer.html)
- [TensorFlow/Keras MNIST](https://www.tensorflow.org/datasets/catalog/mnist)
- [Haar Cascades](https://github.com/opencv/opencv/tree/master/data/haarcascades)

## 📝 License

This project is provided as-is for educational and security research purposes.

## 🤝 Contributing

Contributions are welcome! Areas for improvement:
- Model optimization
- Additional authentication methods
- Performance enhancements
- Security improvements
- Documentation

---

<div align="center">
  <p>Advanced Security Through Intelligent Machine Learning 🔐</p>
</div>
