# ASL Sign Language Alphabet Recognizer

A real-time American Sign Language (ASL) alphabet recognizer built using **Python, TensorFlow, OpenCV, and pyttsx3**.  
The project captures hand gestures through the webcam, predicts the signed alphabet using a trained CNN model, and converts the recognized letters into spoken output.

---

## Features

### **ASL Alphabet Recognition**
- Detects hand gestures (A–Z)
- Uses a trained CNN model (50x50 grayscale images)
- Smooth prediction using confidence thresholds + history

### **Real-Time Translator**
- Live webcam feed with Region of Interest (ROI)
- Displays predicted letter and confidence bar
- Supports sentence building with key controls

### **Text-to-Speech**
- Converts formed sentences into speech using `pyttsx3`

### **Machine Learning**
- Training notebook (`asl.ipynb`) to build the CNN model
- Preprocessing pipeline for hand images
- Generates a `.h5` model file for real-time prediction

---

## 📁 Project Structure

```text
Sign-Language-Recognizer/
│
├── asl.ipynb               # Model training notebook
├── predict_final.py        # Prediction logic (loads trained model)
├── predict.py              # Prediction pipeline
├── translator.py           # Webcam translator + Text-to-Speech
├── variables.py            # Labels + model path
├── requirements.txt        # Python dependencies
├── images/
│     └── alphabet.png      # ASL reference image
├── model/
│     └── model.h5          # (Add later) Trained CNN model file
└── README.md               # Project documentation
```

---

## How to Run the Project

### 1️⃣ Clone the repository
```
git clone https://github.com/Deepthika-Ramasubramaniam/Sign-Language-Recognizer.git
cd Sign-Language-Recognizer
```

### 2️⃣ Install dependencies
```
pip install -r requirements.txt
```

### For Apple Silicon (M1/M2/M3), install:
```
pip install tensorflow-macos
pip install tensorflow-metal
```

---

# 📚 Dataset

The project uses the **ASL Alphabet dataset** containing:

- 26 classes (A to Z)  
- ~700 images per class  
- ~18,200 total images  
- RGB images resized to **64×64×3** for training  

Dataset link:  
https://www.kaggle.com/datasets/ayuraj/asl-dataset

---

# 🧠 Training the Model

Training is performed in the notebook:

```
asl.ipynb
```

The final trained model is saved as:

```
model.keras
model.h5
```

### After training, update `variables.py`:

```
MODEL_PATH = "model.keras"
THRESHOLD = 75
IMAGE_SIZE = 64
LABELS = ['A','B','C', ..., 'Z']
```

---

# 🔍 Prediction Pipeline

`predict.py` handles:

- Image preprocessing (resize → RGB → normalization)  
- Preparing image for CNN input  
- Running the model to get class probabilities  
- Returning predicted label and confidence  

### Usage example:
```python
from predict import which
confidence, letter = which(image)
```

---

# 🎥 Real-Time Translator

Run the translator:

```
python translator.py
```

### Features:

- Live webcam feed  
- Mirrored camera view  
- Large Region of Interest (ROI)  
- Skin-mask-based background removal  
- Display of predicted letter and confidence  
- Sentence assembly and display bar  
- Integrated offline text-to-speech (pyttsx3)

---

## ⌨️ Controls (Keyboard Shortcuts)

| Key | Action |
|-----|--------|
| **N** | Add current predicted letter to sentence |
| **M** | Add space |
| **D** | Delete last character |
| **C** | Clear sentence |
| **S** | Speak the full sentence |
| **ESC** | Quit the translator |

---

## Requirements

- Python 3.8+
- TensorFlow / Keras
- OpenCV
- NumPy
- pyttsx3

---

## Contributors

This project was developed collaboratively by:
- **Deepthika Ramasubramaniam**
- **Rithumiga**
- **Samicamitraa**

---

## License

This project is licensed under the MIT License.  
Refer to the [LICENSE](LICENSE) file for full details.
