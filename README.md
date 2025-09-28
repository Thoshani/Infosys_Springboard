
The goal of this project is to:
1. Load and preprocess textual data from different sources (files or URLs).
2. Generate **summaries** using pretrained models (T5, BART, PEGASUS).
3. Perform **paraphrasing** using multiple approaches (PEGASUS, T5-Paraphrase, BART-Paraphrase).
4. Measure **semantic similarity** between original, summarized, and paraphrased texts using SentenceTransformer.
5. Compare and analyze results across different models.

---
##  Approach
1. **Library Setup** – Installed and imported required libraries (Transformers, SentenceTransformers, etc.).
2. **Model Loading**  
   - Summarization: T5, BART, PEGASUS  
   - Paraphrasing: PEGASUS, T5-Paraphrase, BART-Paraphrase  
   - Similarity: SentenceTransformer (e.g., `all-MiniLM-L6-v2`)
3. **Text Input Processing** –  
   - Load text data (from URL or file).  
   - Clean and preprocess input.  
4. **Summarization** – Apply different summarization models and compare outputs.  
5. **Paraphrasing** – Generate multiple paraphrased variations for each text.  
6. **Similarity Analysis** – Compute cosine similarity between original and generated outputs to evaluate quality.  

---

##  Methodology
1. **Preprocessing**  
   - Remove unwanted characters and clean raw text.  
   - Tokenize input text for model compatibility.  

2. **Summarization**  
   - Use each summarization model separately.  
   - Compare results based on conciseness and readability.  

3. **Paraphrasing**  
   - Generate variations using PEGASUS, T5, and BART.  
   - Collect multiple paraphrases for each input text.  

4. **Similarity Checking**  
   - Represent text embeddings using SentenceTransformer.  
   - Compute cosine similarity between:  
     - Original vs. Summary  
     - Original vs. Paraphrase  
     - Summary vs. Paraphrase  

5. **Evaluation**  
   - Compare similarity scores to measure semantic preservation.  
   - Record qualitative observations on fluency, grammar, and redundancy.  

---

## Observations
- **Summarization**  
  - T5 produced concise summaries but sometimes missed context.  
  - BART generated more fluent and context-aware summaries.  
  - PEGASUS was strong in abstractive summarization, producing natural results.  

- **Paraphrasing**  
  - PEGASUS paraphrased with high semantic retention.  
  - T5-Paraphrase sometimes produced shorter variants.  
  - BART-Paraphrase balanced fluency and semantic preservation.  

- **Similarity Analysis**  
  - Summaries had lower similarity scores compared to paraphrases (expected since summarization is more reductive).  
  - Paraphrases consistently achieved high similarity with the original (0.85–0.95).  
  - PEGASUS outputs had the highest overlap with human-readable meaning.  

---

##  Results
- Multiple models successfully generated high-quality summaries and paraphrases.  
- SentenceTransformer effectively quantified semantic similarity.  
- Ensemble comparison gave insights into the strengths/weaknesses of each model.  

---
You can install all dependencies via:
##  Dependencies
- Python 3.10+  
- Transformers (pip install transformers`)  
- SentenceTransformers (pip install sentence-transformers`)  
- Torch (pip install torch`)  
- Pandas, NumPy  

# Clone the repository
git clone https://github.com/Thoshani/Infosys_Springboard.git
cd Infosys_Springboard

# Install dependencies
pip install -r requirements.txt

# Run the notebook
jupyter notebook final.ipynb


# Run the notebook
jupyter notebook final.ipynb
