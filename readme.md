# **Multi-Hop RAG System**

## **📌 What This Project Does**

This project builds a **Retrieval-Augmented Generation (RAG)** system that can answer **multi-hop questions**.
It reads a set of documents, converts them into embeddings, stores them in **FAISS**, retrieves relevant chunks for a query, and generates final answers using an **LLM**.

It can answer questions that require combining **multiple documents**, for example:

* “Which airline had the highest cancellations and what caused them?”
* “Which carrier improved on-time performance despite rising delays?”

---

## **📌 Steps Performed**

### **1. Load & preprocess documents**

* Reads raw text files
* Splits them into clean chunks
* Prepares text for embedding

### **2. Create embeddings**

* Uses **OpenAI embedding model** to convert text into numeric vectors

### **3. Store embeddings in FAISS**

* Build a FAISS index
* Save metadata (chunk text + source file)

### **4. Retrieve relevant chunks**

* For a given question, retrieve **top K** relevant text chunks

### **5. Multi-hop reasoning**

* Combine information from multiple sources
* Send to an LLM with a structured prompt
* The LLM performs reasoning using only retrieved data

### **6. Produce final answer**

* LLM outputs a clear answer
* Supports complex multi-step or cross-document questions

---

## **📌 Technologies Used**

* **Python**
* **FAISS** (vector search)
* **OpenAI Embeddings** (text embedding)
* **OpenAI GPT Models** (answer generation)
* **Text preprocessing tools** (NLTK / regex)

---

## **📌 Output**

The system outputs:

* Retrieved relevant text chunks
* Final combined answer produced by the LLM
* Uses multi-hop reasoning to connect facts
* No hallucination — answers come only from retrieved context

Example output:

```
Answer:
Spirit Airlines had the most cancellations in 2024 due to fleet grounding
and operational disruptions. Alaska Airlines and Frontier followed due to
weather-related issues.
```
