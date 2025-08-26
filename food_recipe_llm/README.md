# Food Recipe Retrieval-Augmented Generation (RAG with LangChain + Hugging Face)

## Overview
This project implements a **Retrieval-Augmented Generation (RAG)** pipeline to generate high-quality recipes in response to user queries (e.g., *“pizza recipe”*, *“pasta recipe”*).  
It uses a **Phi-3 language model** for text generation, combined with **LangChain**, **FAISS vector database**, and **MiniLM embeddings** for context retrieval from a **2.2M recipe dataset**.

---

## Dataset
- **Source:** [RecipeNLG (Kaggle)](https://www.kaggle.com/datasets/paultimothymooney/recipenlg)  
- **Data Used:** Title, ingredients, and directions combined into a single document per recipe  
- **Subset:** First 100k rows used for efficiency in Colab  

---

## Process
1. **Data Source & Setup**
   - Mounted dataset from Google Drive in Colab  
   - Installed dependencies (`transformers`, `langchain`, `faiss-cpu`, `sentence-transformers`)  

2. **Model Loading**
   - Base LLM: `microsoft/Phi-3-mini-128k-instruct`  
   - Loaded with quiet settings (no widget outputs / log spam)  

3. **Embeddings for Chunking**
   - Embedding model: `all-MiniLM-L6-v2` from `sentence-transformers`  
   - Used for vectorizing both recipes and user queries  

4. **Data Cleaning**
   - Combined each recipe’s **title, ingredients, and directions** into a single text block  
   - Converted to list of strings for ingestion into FAISS  

5. **Vector Database**
   - Indexed recipe embeddings with FAISS  
   - Saved/loaded FAISS index to avoid recomputation  

6. **Retriever & Pipeline**
   - Top-3 nearest vectors retrieved per query (`k=3`)  
   - Hugging Face pipeline for text generation (max tokens=512, temperature=0.1)  
   - Wrapped in LangChain’s `RetrievalQA` chain  

7. **Prompt Template**
   - Custom prompt enforces recipe structure:  
     ```
     Title: <title>
     Ingredients:
     - ...
     Directions:
     1. ...
     2. ...
     ```  

8. **Interactive Display**
   - Loop allows users to input recipe queries directly  
   - Model returns structured recipes generated from retrieved context  

---

## Results
Sample queries demonstrate accurate recipe generation grounded in the dataset:

- **Query:** *pizza recipe*  
  → Generated **Classic Margherita Pizza** with correct ingredients and step-by-step directions.  

- **Query:** *pasta recipe*  
  → Generated **Creamy Mushroom Spinach Pasta**, including pasta water tip.  

- **Query:** *salad recipe*  
  → Generated **Classic Cobb Salad**, with optional dressings and customization notes.  

These outputs verify that the system is not “hallucinating freely” but instead retrieving and formatting authentic recipes.



