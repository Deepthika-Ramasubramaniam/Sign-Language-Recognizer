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
├── translator.py           # Webcam translator + Text-to-Speech
├── variables.py            # Labels + model path
├── requirements.txt        # Python dependencies
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

### 3️⃣ Add the trained model
Place your trained model file inside:

```
model/model.h5
```

If you don’t have the model yet, open and run the `asl.ipynb` notebook:

```
model.save("model/model.h5")
```

### 4️⃣ Run the ASL Translator
```
python translator.py
```

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
