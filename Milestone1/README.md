# TextMorph: Summarization, Paraphrasing, and Similarity Analysis

TextMorph is a natural language processing (NLP) project that integrates **summarization**, **paraphrasing**, and **semantic similarity** analysis into one unified workflow.  

Using state-of-the-art transformer models (T5, BART, PEGASUS, and Sentence Transformers), this project demonstrates how different models perform on the same text and provides visualization tools to compare their outputs.

##  Overview
Large language models can summarize or paraphrase text in many different ways.  
But **how do their results compare?**  

TextMorph answers this question by:
- Running multiple **summarization models** on the same text.
- Generating **paraphrased versions** of the summaries.
- Measuring **similarity scores** against the original text.
- Visualizing the differences in **length, style, and content**.
- Performing **bigram analysis** to reveal common word pair patterns.

This project is structured as a **Jupyter Notebook (`FINAL.ipynb`)**, organized into modular parts.


##  Project Structure
The notebook is divided into clear sections:

### **0. Setup**
- Install and import all required libraries.
- Load summarization models (T5, BART, PEGASUS).
- Load paraphrasing models (same set).
- Load a similarity model (`SentenceTransformer`).

### **1. Text Input Processing**
- Load and validate single or multiple text files.
- Prepare raw text for processing.

### **2. Core Analysis Components**
- Functions for:
  - **Summarization** with T5, BART, and PEGASUS.
  - **Paraphrasing** with PEGASUS, T5, and BART.
  - **Similarity analysis** using cosine similarity.

### **3. Enhanced Model Comparison**
- Compare models on:
  - Summary length
  - Similarity to original text
- Side-by-side comparison of generated outputs.

### **4. Integrated TextMorph Pipeline**
- End-to-end workflow:
  - Input → Summarization → Paraphrasing → Similarity → Results.

### **5. Testing**
- Apply pipeline to multiple reference text files.
- Evaluate how different models perform on different inputs.

### **6. Visualization & Insights**
- Graphical comparison of:
  - Summarization metrics
  - Paraphrasing metrics

### **7. Bigram Analysis**
- Extract frequent **bigrams** (two-word sequences).
- Visualize them for linguistic insights.



##  Installation
Clone the repository and install dependencies:


git clone https://github.com/Thoshani/Infosys_Springboard/blob/main/Milestone1/finalproject.ipynb
cd finalproject

pip install -r requirements.txt


If `requirements.txt` is missing, install manually:

pip install transformers sentence-transformers scikit-learn matplotlib


##  Usage
1. Open the notebook:
   jupyter notebook FINAL.ipynb 
2. Run the cells in order.
3. Provide your own text files (or use the sample ones).
4. View generated:
   - Summaries
   - Paraphrases
   - Similarity metrics
   - Visualizations


## Example Workflow
Here’s a typical pipeline run:

1. **Input Text**: A paragraph or full document.
2. **Summarization**:
   - T5 → short, concise summary
   - BART → structured summary
   - PEGASUS → abstractive summary
3. **Paraphrasing**:
   - Each summary is rewritten differently.
4. **Similarity Scoring**:
   - Compare summaries & paraphrases with original text.
5. **Visualization**:
   - Bar charts for length and similarity.
   - Bigram charts for frequent patterns.



##  Outputs
- **Summaries**: Multiple model outputs for the same input.
- **Paraphrases**: Alternative phrasings of summaries.
- **Metrics**:  
  - Length of summaries.  
  - Cosine similarity with original text.  
- **Plots**:  
  - Model comparison bar charts.  
  - Bigram visualizations.

- `README.md` — Project documentation.  
- `requirements.txt` — List of dependencies.  
