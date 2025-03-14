# Multi-Modal Deep Learning Framework for Disease Detection  

## Motivation 
In modern healthcare, accurate disease diagnosis often requires analyzing **multiple data modalities**—such as **radiology images (X-rays) and clinical reports (text notes)**—to form a comprehensive understanding of a patient’s condition.  

Traditional **single-modality models** (image-based or text-based) fail to capture the full spectrum of diagnostic cues, leading to **incomplete or inaccurate predictions**.  

To **mimic real-world medical decision-making**, we propose a **Multi-Modal Deep Learning Framework for Disease Detection** that **fuses radiology images and textual clinical notes** to improve diagnostic accuracy and interpretability.  

The framework consists of:  
✔ **CNN-based Image Branch (EfficientNet)** for chest X-ray analysis  
✔ **Transformer-based Text Branch (PubMedBERT)** for clinical report understanding  
✔ **Feature Fusion Model (Fully Connected Neural Network - FC-FNN)** to combine both modalities  

By integrating **visual patterns from chest X-rays** and **semantic insights from clinical reports**, this model **mimics how doctors diagnose diseases** in real-world clinical settings.

---

## Architecture  

### **System Overview** 
Our multi-modal deep learning framework consists of three main components: 
1. **Chest X-ray Image Processing**: Uses **EfficientNet** for feature extraction  
2. **Clinical Notes Processing**: Uses **PubMedBERT** for text representation  
3. **Feature Fusion**: Combines extracted features using **FC-FNN** for final disease classification  

### **System Architecture Diagram**  
![Architecture](https://github.com/adijad/Multi-Modal-Deep-Learning-Framework-for-Disease-Detection/blob/main/Dataset/Blank%20board%20-%20Page%201%20(2)%20(1).png)

## Model Workflow
### **1. Image Processing (CNN - EfficientNet)**
- **Input:** Chest X-ray images (preprocessed).  
- **Feature Extraction:**  
  - EfficientNet is **pre-trained on medical images** and fine-tuned on **MIMIC-CXR dataset**.  
  - It **detects visual markers** like lung opacity, cardiomegaly, or pleural effusion.  
- **Output:** A **high-dimensional feature vector** representing the image.  

**Why EfficientNet?**  
- Uses **compound scaling** (depth, width, and resolution) to optimize performance.  
- Achieves **higher accuracy with fewer parameters** compared to traditional CNNs.  

---

### **2. Clinical Notes Processing (Transformer - PubMedBERT)**
- **Input:** Doctor's text-based **clinical reports**.  
- **Feature Extraction:**  
  - Tokenized and **embedded using PubMedBERT** (fine-tuned on biomedical text).  
  - Passed through a **Bidirectional LSTM (Bi-LSTM)** to capture **medical context**.  
- **Output:** A **text feature vector** representing the **semantic meaning** of the report.  

**Why PubMedBERT?**  
- Specifically **pre-trained on medical literature** for better **biomedical language understanding**.  
- Captures **domain-specific nuances** (e.g., "ground-glass opacity" → **Pneumonia**).  

---

### **3. Feature Fusion (FC-FNN)**
- **Input:**  
  - **Image feature vector** (from EfficientNet).  
  - **Text feature vector** (from PubMedBERT + LSTM).  
- **Concatenation:**  
  - Merged into a **common latent space** to capture cross-modal relationships.  
- **Classification:**  
  - Fully Connected Neural Network (FC-FNN) performs **final disease classification**.  
  - Uses **sigmoid activation** for **multi-label disease detection**.
---

## Dataset  
We use **MIMIC-CXR**, a publicly available dataset containing **377,110 chest radiographs** and associated **clinical reports** from **Beth Israel Deaconess Medical Center (2011-2016)**.  

- **Preprocessing**:  
  - X-ray images resized to **224×224 pixels** and normalized  
  - Clinical reports tokenized and processed for **BERT-based embeddings**

Example Chest X-ray and Radiology Report:  
![X-ray Report](https://github.com/adijad/Multi-Modal-Deep-Learning-Framework-for-Disease-Detection/blob/main/Dataset/DLProjectimage.png)
