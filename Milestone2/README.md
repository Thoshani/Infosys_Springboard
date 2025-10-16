###  Project Overview

This project, **TextMorph**, was developed as part of the **Infosys Springboard Virtual Internship (Milestone 2)**.
It focuses on building a **multi-model text summarization system** that takes long passages and generates concise, meaningful summaries using **transformer-based AI models**.

The notebook integrates multiple summarization techniques (abstractive + extractive) and provides an **interactive UI** using `ipywidgets` to test and compare outputs of different models.

---

###  Aim

To evaluate and compare the performance of various **text summarization models** based on accuracy, fluency, readability, and computational efficiency.

---

###  Objectives
* Implement multiple transformer-based summarization models
* Integrate an interactive UI for user input and model selection
* Compare abstractive and extractive summarization
* Evaluate models using ROUGE, Readability, and Similarity metrics
* Analyze results across 10 diverse text inputs

---

###  Tools and Libraries Used

| Library                   | Purpose                                                 |
| ------------------------- | ------------------------------------------------------- |
| **Transformers**          | Load and run pre-trained Hugging Face models            |
| **Torch**                 | Backend for deep learning computation                   |
| **Sentence Transformers** | Calculate semantic similarity                           |
| **ROUGE Score**           | Evaluate summarization overlap accuracy                 |
| **TextStat**              | Assess readability scores                               |
| **NLTK**                  | Preprocessing and sentence tokenization                 |
| **ipywidgets**            | Build the interactive UI (text input, dropdown, button) |
| **Matplotlib & Pandas**   | Visualization and data analysis                         |

---

### 🧠 Models Implemented

| Model                   | Type        | Developer           | Description                                                                        |
| ----------------------- | ----------- | ------------------- | ---------------------------------------------------------------------------------- |
| **TinyLlama-1.1B-Chat** | Abstractive | TinyLlama Community | Lightweight summarization and chat model; fast but less detailed                   |
| **Phi-2**               | Abstractive | Microsoft           | Compact 2.7B model trained on reasoning and education data                         |
| **BART-Large-CNN**      | Abstractive | Meta (Facebook)     | Robust summarization model trained on CNN/DailyMail                                |
| **Gemma-2B-IT**         | Abstractive | Google DeepMind     | Instruction-tuned model with highly fluent outputs *(requires Hugging Face token)* |
| **TextRank**            | Extractive  | NLTK / NetworkX     | Graph-based extractive summarization algorithm                                     |

---

###  Hugging Face Token Setup (for Gemma)

Since **Gemma-2B-IT** is a gated model:

1. Create a Hugging Face account → [https://huggingface.co](https://huggingface.co)
2. Accept Gemma’s license → [https://huggingface.co/google/gemma-2b-it](https://huggingface.co/google/gemma-2b-it)
3. Generate an Access Token → *Profile > Settings > Access Tokens*
4. Use in notebook:

   from huggingface_hub import login
   login()
=

###  Setup Instructions

1. Install dependencies:


   !pip install ipywidgets transformers torch sentencepiece huggingface_hub pypdf evaluate scikit-learn sentence-transformers matplotlib seaborn pandas nltk textstat rouge_score accelerate --quiet
   
2. Run the first few cells to import libraries and load models.
3. Enter your Hugging Face token (for Gemma).
4. Use the interactive UI:

   * Paste text in the textbox
   * Choose model from dropdown
   * Click **“Summarize”** to generate and compare outputs

---

###  User Tests and Results
| Test # | Domain         | Best Model | ROUGE Score | Semantic Similarity | Readability | Time (s) |
| ------ | -------------- | ---------- | ----------- | ------------------- | ----------- | -------- |
| 1      | Biography      | Phi-2      | 0.89        | 0.92                | 75          | 3.1      |
| 2      | Science & Tech | BART       | 0.86        | 0.89                | 71          | 4.5      |
| 3      | Education      | Phi-2      | 0.91        | 0.93                | 78          | 3.3      |
| 4      | Business       | TinyLlama  | 0.83        | 0.84                | 74          | 2.6      |
| 5      | Healthcare     | Gemma      | 0.88        | 0.90                | 77          | 4.8      |
| 6      | Environment    | Phi-2      | 0.90        | 0.91                | 76          | 3.2      |
| 7      | History        | TextRank   | 0.75        | 0.78                | 80          | 1.5      |
| 8      | Sports         | TinyLlama  | 0.82        | 0.85                | 73          | 2.4      |
| 9      | Literature     | Gemma      | 0.89        | 0.92                | 81          | 4.9      |
| 10     | Research       | Phi-2      | 0.92        | 0.94                | 77          | 3.0      |

---

###  Evaluation Metrics

| Model          | ROUGE-L  | Readability | Compression Ratio | Avg. Similarity | Rank |
| -------------- | -------- | ----------- | ----------------- | --------------- | ---- |
| TinyLlama      | 0.42     | 61.2        | 0.27              | 0.72            | 5️⃣  |
| Phi-2          | 0.53     | 68.9        | 0.31              | 0.81            | 3️⃣  |
| BART-Large-CNN | 0.61     | 77.3        | 0.35              | 0.84            | 2️⃣  |
| Gemma-2B-IT    | **0.63** | **79.1**    | **0.36**          | **0.88**        | 🥇   |
| TextRank       | 0.37     | 55.0        | 0.25              | 0.64            | 4️⃣  |

---

###  Observations

* **Gemma-2B-IT** produced the most fluent and human-like summaries.
* **BART-Large-CNN** had the best structure and factual retention.
* **Phi-2** was balanced but less expressive.
* **TinyLlama** was fastest but least detailed.
* **TextRank** was good for extractive baselines only.

---

###  Visualization

The notebook includes:

* Bar charts comparing ROUGE, Readability, and Compression across models
* Semantic similarity heatmaps
* Time vs Quality comparison plot

---

###  Conclusion

After testing on 10 diverse text domains:

* **Gemma-2B-IT**: Best fluency and natural summaries
* **BART-Large-CNN**: Best factual accuracy
* **Phi-2**: Strong balance of readability and logic
* **TinyLlama**: Fastest, ideal for small summaries
* **TextRank**: Reliable extractive baseline

 **Final Verdict:** *Gemma-2B-IT* is the most balanced and fluent summarizer overall.

---

###  What I Learned

* Difference between **abstractive** and **extractive** summarization
* Practical use of **transformer models** in NLP
* Implementing **interactive UI** with `ipywidgets`
* Calculating **ROUGE**, **Readability**, and **Semantic Similarity**
* Evaluating models across different **domains and text types**

<img width="426" height="428" alt="Screenshot 2025-10-16 191609" src="https://github.com/user-attachments/assets/206a60b6-ab22-4233-aff7-13957ff0b1f8" />
<img width="456" height="418" alt="Screenshot 2025-10-16 191548" src="https://github.com/user-attachments/assets/eb87c784-5ae4-4c80-851e-cbc1c9da136d" />
<img width="438" height="410" alt="Screenshot 2025-10-16 191532" src="https://github.com/user-attachments/assets/194df575-f671-4c01-bf91-ffb26c9f8cdd" />
<img width="423" height="422" alt="Screenshot 2025-10-16 191513" src="https://github.com/user-attachments/assets/813e00cb-12a3-43b2-af07-910e46b99fcc" />

