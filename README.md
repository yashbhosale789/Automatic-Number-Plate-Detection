# Automatic Number Plate Detection 🚘

![Preview](https://i.postimg.cc/rFTXByg8/Screenshot-2023-05-28-001749.png)

The goal of this project was to create a model that can accurately detect number plates on cars and bikes. This model can be used along with the video data generated from CCTV cameras that are installed on highways and roadways to detect number plates of vehicles that commit traffic violations.

## ℹ️ Model Information

Object Detection is carried out in this project to detect Number Plates on vehicles. The **YOLOv5s** model was used along with transfer learning for training and testing. The model accurately generates bounding boxes around Number Plates.

More Info on YOLOv5: [YOLOv5 GitHub Repo](https://github.com/ultralytics/yolov5)

## 📚 Dataset

The dataset used for training for Number Plate detection:  

- [Kaggle: Car Number Plate Detection](https://www.kaggle.com/datasets/elysian01/car-number-plate-detection)

## ✍️ Installation

Install `requirements.txt` in a **Python >= 3.7.0** environment.

```sh
git clone https://github.com/KALYAN1045/Automatic-Number-Plate-Recognition-using-YOLOv5.git  # Clone repo
cd Automatic-Number-Plate-Recognition-using-YOLOv5
pip install -r requirements.txt  # Install dependencies
```

## 🔐 Implementation

The Object Detection pipeline consists of **Training, Validation, and Testing**.

### Training:

**YOLOv5s** was trained on Google Colab with the following hyperparameters:

- **Input Image Size:** 640  
- **Batch Size:** 16  
- **Epochs:** 300 (converged in 198 epochs)  
- **Pretrained Weights:** yolov5s.pt  

The training dataset consisted of **400 images** with class and bounding box details in YOLO format. The training was set to run for **300 epochs**, but it **converged at 198 epochs**.

### Validation:

The validation dataset consisted of **100 images** with bounding box details. The model achieved a **Mean Average Precision (mAP) of 0.91**.

**Validation results:**
![Validation](https://raw.githubusercontent.com/wasdac9/automatic-number-plate-recognition/main/val_pred.jpg)

At the end of training, a weights file (`best.pt`) is generated. Refer to `ANPD_OD.ipynb` for details on training and validation.

### Testing Phase

The model was tested on **various images and videos**, generating accurate bounding box predictions. Testing was carried out in **PyTorch** using **OpenCV** for handling images and videos.

## 📦 Result

![Result](https://i.postimg.cc/G2tR6KCw/result.png)

## 📚 Summary

An accurate **Automatic Number Plate Recognition (ANPR)** model was created using **YOLOv5 and transfer learning** in PyTorch. The model achieved **high accuracy and good frame rate**.

## 🚩 Limitations
- The model **sometimes detects road signs as number plates**. A **larger dataset** is needed to improve accuracy.  
- It performs **well on CUDA GPUs (32 FPS)** but **poorly on CPU devices**.  
- It **struggles with detecting bike plates** due to **camera quality and variations**.

## 🚀 Future Work
- Train the model on a **larger dataset** for better generalization.  
- Deploy the model on **edge devices** for real-time Number Plate Recognition.  
- Use **OCR (Optical Character Recognition)** to read detected number plates.  

## ♨️ Tech Stack

![TensorFlow](https://img.shields.io/badge/TensorFlow-%23FF6F00.svg?style=for-the-badge&logo=TensorFlow&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white)
