# Myanmar-Agri-Med-AI

## 1. Introduction
The **Myanmar Agri-Med AI** is a Retrieval-Augmented Generation (RAG) system designed to provide localized agricultural and medical advice in the Burmese language. It utilizes a fine-tuned Sentence-Transformer model and FAISS vector indices to ensure factual accuracy and high-speed retrieval.

## 2. Pre-Requisites
Before running the application, ensure your environment meets the following requirements:

### Hardware Requirements
* **RAM:** Minimum 8GB (16GB recommended for smooth model loading).
* **Storage:** 1GB of free space for the model and vector indices.
* **Internet:** Required only for the initial installation of libraries.

### Software Requirements
* **Python:** Version 3.10 or higher.
* **Required Libraries:** Install the following packages using pip:
    ```bash
    pip install streamlit pandas faiss-cpu sentence-transformers torch
    ```

## 3. Project Structure & Files
Ensure your folder is structured exactly as follows for the script to locate the models and data:

* `streamlit_app.py` (The main UI script)
* `fine_tuned_burmese_model/` (The folder containing model weights and config)
* `agriculture_faiss.index` / `agriculture_answers.pkl` (Agri Knowledge Base)
* `medicine_faiss.index` / `medicine_answers.pkl` (Medical Knowledge Base)

## 4. Step-by-Step Execution Guide

### Step 1: Open Terminal/Command Prompt
Navigate to the root directory where you have extracted the project files.
```bash
cd path/to/your/project_folder

### Step 2: Launch the Streamlit Application
Run the following command to start the local web server.

```bash
streamlit run streamlit_app.py

### Step 3: Access the Interface
Once the command is executed, Streamlit will automatically open a new tab in your default web browser (usually at http://localhost:8501).

---

## 5. Interacting with the System

### A. Selecting a Domain
Use the **Sidebar** on the left to toggle between **Medicine** and **Agriculture**. The AI will switch its knowledge base (FAISS index) instantly based on this selection.

### B. Inputting Queries
Type your question in the chat input box at the bottom. The system is optimized for Burmese Unicode.

* **Example for Agri:** "သစ်ပင်စိုက်ပျိုးရန် မြေကို ဘယ်လိုပြင်ဆင်ရမလဲ?" *(How to prepare the soil for planting trees?)*
* **Example for Med:** "အဏုဇီဝဗေဒဆိုတာ ဘာလဲ ရှင်းပြပါ" *(What is Microbiology?)*
* **Greetings:** You can also input greeting queries such as "hi", "Hello", or "မင်္ဂလာပါ".

### C. Safety Features
* **Similarity Threshold:** If you ask a question outside the knowledge base (e.g., "Who won the football match?"), the system will respond with a fallback message: "တောင်းပန်ပါတယ်၊ အဲဒီအကြောင်းအရာနဲ့ ပတ်သက်ပြီး ကျွန်တော့် ဒေတာထဲမှာ မတွေ့ပါဘူး။" *(Sorry, I don't have this data)*.
* **Medical Disclaimer:** All medical responses automatically include a legal disclaimer at the bottom.

### D. Managing Conversation
* **Clear Chat:** Click the "**🗑️ Clear Chat**" button in the sidebar to reset the session.
* **Download History:** Click "**📥 Download**" to save the current conversation as a .txt file for offline reference.

---

## 6. Troubleshooting
* **Model Not Loading:** Ensure the `fine_tuned_burmese_model` folder name matches exactly and is in the same directory as the script.
* **Burmese Font Issues:** If text appears as boxes, ensure your operating system has a standard Burmese Unicode font (like Pyidaungsu or Padauk) installed.
* **Faiss Error:** If you are on an M1/M2 Mac, use `pip install faiss-cpu` specifically.
