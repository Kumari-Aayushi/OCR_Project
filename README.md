# 📘 Advanced Offline OCR System (TrOCR + Tesseract + OpenCV)

A complete, production-ready Optical Character Recognition (OCR) system combining **Transformer-based OCR (TrOCR)** with classical OCR (Tesseract). This project is designed for extracting text from **medical documents, prescriptions, lab reports, handwritten samples, scene text**, and **scanned PDFs**, supporting both **English and Hindi**.

This system is built for real-world environments where documents are noisy, skewed, low-resolution, or contain complex structures.

---

# 📑 Table of Contents

* Overview
* Motivation
* Key Features
* System Architecture
* Models Used
* Preprocessing Pipeline
* Demo Notebook
* Getting Started
* Project Structure
* Datasets
* Results & Benchmarks
* Future Enhancements
* Contact

---

# 🌍 Overview

This project implements two powerful OCR pipelines:

### **1️⃣ Offline OCR Pipeline (Tesseract + OpenCV)**

* Works **100% offline**
* Ideal for printed text, forms, and structured documents
* Uses OpenCV preprocessing to boost accuracy
* Supports image + PDF OCR

### **2️⃣ Transformer-Based OCR (TrOCR - Microsoft Research)**

* Modern, SOTA deep learning OCR based on **Vision Transformers (ViT) + GPT-style decoder**
* Excels on handwriting, low-quality images, and irregular text
* Handles complex documents extremely well

The project allows users to run both pipelines, compare results, and use them based on their needs.

---

# ⭐ Key Features

### 🔍 Multi-Engine OCR System

* **TrOCR (Transformer OCR)** – High accuracy, deep-learning based
* **Tesseract OCR** – Fast, offline
* **EasyOCR / PaddleOCR (optional)** – Multilingual

### 🧹 Powerful Preprocessing Pipeline (OpenCV)

Includes:

* Grayscale
* Noise removal
* Thresholding (Otsu / adaptive)
* Dilation / erosion
* Contour detection
* Image deskewing
* ROI extraction

### 📄 Document Support

* Images: JPG / PNG
* Scanned PDFs (multi-page)
* Medical reports
* Prescriptions
* Scene text
* Handwritten English text
* Hindi printed text

### 🧪 Medical Text Extraction

Extracts:

* Patient name
* Test names
* Values (mg/dL, mmol/L)
* Reference ranges

---

# 🎯 Motivation

Traditional OCR tools like Tesseract struggle with:

* Noisy images
* Shadows, blur, artifacts
* Handwritten text
* Mixed languages
* Scene text

This project solves these limitations by combining:

* Classical OCR
* Deep learning (TrOCR)
* Strong preprocessing
* Multiple benchmark datasets

The objective is to produce a **high-accuracy, robust OCR engine** that works across real-world conditions.

---

# 🏗️ System Architecture

```
Input Image/PDF
      ↓
Preprocessing (OpenCV)
      ↓
 ┌───────────────┬────────────────┐
 │               │                │
Tesseract OCR   TrOCR (Transformer)
 │               │
 └───────────────┴────────────────┘
      ↓
Post-processing
      ↓
Structured Output
```

---

# 🤖 Models Used

### **1️⃣ TrOCR (Microsoft Research)**

* Vision Transformer Encoder (ViT)
* GPT-2 style text decoder
* Excellent for handwriting and scene text

### **2️⃣ Tesseract OCR**

* Offline engine
* Ideal for clean printed text

### **3️⃣ (Optional) PaddleOCR / EasyOCR**

* Multilingual text extraction

---

# 🧹 Preprocessing Pipeline Overview

The notebook applies the following steps:

* Resize & denoise
* Adaptive thresholding
* Otsu binarization
* Morphological operations
* Deskewing using Hough transform
* Contour detection for cropping text regions
* Sharpening + smoothing

These drastically improve OCR quality.

---

# 📊 Demo Notebook

Your project contains:

### 📁 `Offline_OCR.ipynb`

A complete Colab-ready notebook including:

* Upload interface
* Preprocessing preview
* Tesseract OCR extraction
* TrOCR inference
* PDF page-to-image conversion
* Side-by-side model comparison

---

# ⚙️ Getting Started

## 📌 Install Dependencies

```
pip install pytesseract opencv-python pillow transformers torch pdf2image easyocr
```

## 📌 Install Tesseract Engine

Windows, Linux, and Mac instructions vary; follow official documentation.

## ▶️ Run Notebook

Open `Offline_OCR.ipynb` in Google Colab or Jupyter Notebook.

---

# 📂 Project Structure

```
📁 OCR_Project
│── Offline_OCR.ipynb
│── TrOCR.pdf
│── samples/
│── outputs/
│── README.md
│── requirements.txt
```

---

# 🧪 Datasets Used

This project aligns with the following datasets:

* **IIIT5K Word Dataset** – Scene text recognition
* **IAM Handwriting Dataset** – English handwriting
* **GNHK Dataset** – Hindi printed text
* **Devanagari Character Dataset** – Hindi characters
* **Custom medical documents** – Prescriptions & reports

---

# 📈 Results & Benchmarks

| Model                 | Accuracy  | Strengths                              | Best Use                |
| --------------------- | --------- | -------------------------------------- | ----------------------- |
| **Tesseract**         | Medium    | Fast, offline                          | Clean printed text      |
| **TrOCR**             | Very High | Handles noise, handwriting, scene text | Complex documents       |
| **EasyOCR/PaddleOCR** | High      | Multilingual                           | Mixed-language datasets |

---

# 🔮 Future Enhancements

* Fine-tuning TrOCR on custom datasets
* Hindi TrOCR model
* Integration with LayoutLMv3 for form understanding
* Deploying as FastAPI service
* Adding OCR-Diffusion model
* Cloud deployment on AWS/GCP

---

# 📩 Contact

👩‍💻 **Aayushi Kumari**
📧 Email: [preaayushi39@gmail.com)
🔗 GitHub: [https://github.com/Kumari-Aayushi)
🌐 LinkedIn: [https://www.linkedin.com/in/aayushi-kumari-548a4225b?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app)

---

✨ *"Building machines that can see, read and understand the world."*
