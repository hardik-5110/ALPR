
# 🚗 License Plate Detection and OCR using YOLOv8

This project detects vehicle license plates using a custom-trained YOLOv8 model and extracts the plate number using Tesseract OCR.

---

## 🧠 Features

- Trains YOLOv8 for custom object detection (`license-plate`, `vehicle`)
- Draws bounding boxes only around license plates
- Extracts license plate text using Tesseract OCR
- Works with any image input
- Optimized for accuracy using OpenCV preprocessing

---

## 🛠️ Installation (Google Colab)

```bash
# Install dependencies
!pip install -q ultralytics cvzone pytesseract
!apt-get install -y tesseract-ocr
```

---

## 📁 Project Structure

```
/vechical-plate-detection
│
├── data.yml                # YOLO dataset config file
├── images/                 # Training/validation images
│   ├── train/
│   └── val/
├── labels/                 # YOLO labels for each image
│
├── train_model.ipynb       # Notebook to train YOLOv8
├── detect_and_ocr.ipynb    # Detect plates and extract text
├── runs/                   # YOLO training results
```

---

## 🔧 Training the Model

```python
from ultralytics import YOLO

!yolo task=detect mode=train     model=yolov8s.pt     data=/content/vechical-plate-detection/data.yml     epochs=300 imgsz=640
```

---

## 🕵️‍♂️ Inference + OCR

```
import YOLO, pytesseract, cv2, cvzone
Load trained model and image
results
```

---

## 🧠 Model Info

- Model: YOLOv8s
- Framework: Ultralytics
- OCR: Tesseract (via pytesseract)

---

## 📌 TODO

- [ ] Improve OCR post-processing with regex
- [ ] Support real-time webcam inference
- [ ] Export to ONNX for edge devices

---

## 📄 License

feel free to use

---

## 🙌 Acknowledgements

- [Ultralytics YOLOv8](https://github.com/ultralytics/ultralytics)
- [Tesseract OCR](https://github.com/tesseract-ocr/tesseract)
- [cvzone](https://github.com/cvzone/cvzone)
