# *MediMatchAI 🏥💊*  
### *Simplifying Pharmacy Workflows with AI*  

At *MediMatchAI*, we’re working on a simple but powerful idea: helping pharmacists process prescriptions faster and with fewer errors. We know that handwritten prescriptions can be hard to read, and mistakes can lead to serious problems. That’s why we built an AI-powered tool that takes the guesswork out of decoding prescriptions, making things smoother for both pharmacists and patients.

---

## 🌟 *What Does MediMatchAI Do?*  
MediMatchAI is an *AI-powered assistant* that automates the process of reading and interpreting handwritten prescriptions. Here’s how it works:  

1. *Pharmacists upload a photo of a handwritten prescription.*  

 2. *Our AI reads the prescription and extracts medicine names, dosages, and instructions.*

3. *Using BioBERT, we ensure the extracted information is accurate and makes sense in a medical context.*  

4. *We check the medicines against trusted databases to ensure they’re safe and correct.*  

5. *If a medicine is out of stock, we suggest alternatives.*  

6. *Pharmacists review the details, make adjustments if needed, and place the order.*  

---

## *Technical Approach*  

We have built *two independent AI models*, each offering a unique approach to extracting medicine names from handwritten prescriptions.

---

### *1. CRNN (Convolutional Recurrent Neural Network)*  
- *What it does:*  
  - Uses *Convolutional Neural Networks (CNNs)* to analyze handwriting patterns.  
  - Employs *Recurrent Neural Networks (RNNs)* to understand the sequence of characters.  
  - Handles variable-length words using *CTC Loss*, making it effective for messy or faded handwriting.  

- *Why it’s useful:*  
  - Works well for cursive or low-quality prescriptions.  
  - Reliable for real-world use, even with noisy images.  

---

### *2. TrOCR (Transformer-based OCR)*  
- *What it does:*  
  - Uses a *Vision Transformer (ViT)* to process images and extract text features.  
  - Generates text predictions with a *GPT-like decoder*, fine-tuned for handwritten text.  
  - Combines the power of *Tesseract OCR* for bounding box detection and *TrOCR* for text refinement.  

- *Why it’s useful:*  
  - Excels at reading hard-to-decipher handwriting.  
  - Understands context better than traditional OCR.  

---

## *Beyond OCR*  

### *BioBERT: Medical Context Understanding*  
After extracting text, *BioBERT* steps in to:  
- Fix OCR errors (e.g., "Panacl" → "Paracetamol").  
- Understand dosages and instructions (e.g., "2 times daily").  
- Extract only valid drug names from noisy text.  

### *DrugBank API: Medicine Validation*  
We validate medicines against trusted medical databases to:  
- Check for dosage errors or drug conflicts.  
- Ensure patient safety by flagging potential issues.  

### *Inventory Management*  
- If a medicine is in stock, we place the order instantly.  
- If it’s out of stock, we suggest alternatives.  
- Pharmacists can review and confirm before finalizing.  

---

### *Setting Up MediMatchAI Locally*  

1. *Clone the repository:*  
bash
git clone https://github.com/your-repo/pharmassist.git
cd pharmassist




2. *Ensure Jupyter Notebook is installed (if not already):*  
bash
pip install jupyter


3. *Launch Jupyter Notebook:*  
bash
jupyter notebook


4. *Run the notebooks in order:*  
- Open 01_preprocessing.ipynb → Handles *image preprocessing* & *text detection*  
- Open 02_ocr_extraction.ipynb → Runs *OCR & post-processing*  

---

##  *Future Implementations*  
- We plan to replicate the full pipeline shown in the architecture:
- Improve text detection using YOLOv4 + Faster R-CNN
- Enhance OCR models with ViT + CTC for robust recognition
- Implement Layout Analysis using Graph Neural Networks & Spatial CNNs
- Context-based error correction with BioBERT & LayoutLM

---
