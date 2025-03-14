# Multi-Modal Deep Learning Framework for Disease Detection  

## 📌 Overview  
In modern healthcare, accurate disease diagnosis often requires combining **radiology images and clinical reports**. This project proposes a **multi-modal deep learning framework** that integrates both **medical imaging (chest X-rays)** and **text-based clinical notes** to improve disease detection accuracy.  

The framework consists of:  
✔ **CNN-based Image Branch (EfficientNet)** for chest X-ray analysis  
✔ **Transformer-based Text Branch (PubMedBERT)** for clinical report understanding  
✔ **Feature Fusion Model (Fully Connected Neural Network - FC-FNN)** to combine both modalities  

This approach **mimics real-world clinical decision-making** by leveraging the complementary strengths of visual and textual data.  

---

## 🚀 Architecture  

### **Model Workflow**  
1. **Chest X-ray Image Processing**: Uses **EfficientNet** for feature extraction  
2. **Clinical Notes Processing**: Uses **PubMedBERT** for text representation  
3. **Feature Fusion**: Combines extracted features using **FC-FNN** for final disease classification  

### **System Architecture Diagram**  
![Architecture](https://github.com/adijad/Multi-Modal-Deep-Learning-Framework-for-Disease-Detection/blob/main/Dataset/Blank%20board%20-%20Page%201%20(2)%20(1).png) 

---

## 📂 Dataset  
We use **MIMIC-CXR**, a publicly available dataset containing **377,110 chest radiographs** and associated **clinical reports** from **Beth Israel Deaconess Medical Center (2011-2016)**.  

- **Preprocessing**:  
  - X-ray images resized to **224×224 pixels** and normalized  
  - Clinical reports tokenized and processed for **BERT-based embeddings**  
