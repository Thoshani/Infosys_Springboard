TextMorph: Summarization, Paraphrasing, and Similarity Analysis
TextMorph is a natural language processing project that brings together summarization, paraphrasing, and semantic similarity analysis into one complete workflow.
Using state-of-the-art transformer models like T5, BART, PEGASUS, and Sentence Transformers, this project shows how different models perform on the same text and provides tools to compare their outputs visually.

Overview
Large language models can summarize or paraphrase text in many different ways. But how do their results actually compare?
TextMorph answers this question by:

Running multiple summarization models on the same text
Generating paraphrased versions of the summaries
Measuring similarity scores against the original text
Visualizing the differences in length, style, and content
Performing bigram analysis to reveal common word pair patterns

The notebook is divided into clear sections:

0. Setup

Install and import all required libraries
Load summarization models: T5, BART, and PEGASUS
Load paraphrasing models using the same set
Load a similarity model using SentenceTransformer

1. Text Input Processing

Load and validate single or multiple text files
Prepare raw text for processing

2. Core Analysis Components

Functions for summarization with T5, BART, and PEGASUS
Functions for paraphrasing with PEGASUS, T5, and BART
Similarity analysis using cosine similarity

3. Enhanced Model Comparison

Compare models based on summary length
Compare similarity to original text
Side-by-side comparison of generated outputs

4. Integrated TextMorph Pipeline

Complete end-to-end workflow from input to results
Input text goes through summarization, paraphrasing, similarity analysis, and results generation

5. Testing

Apply pipeline to multiple reference text files
Evaluate how different models perform on different inputs

6. Visualization and Insights

Graphical comparison of summarization metrics
Graphical comparison of paraphrasing metrics

7. Bigram Analysis

Extract frequent bigrams, which are two-word sequences
Visualize them for linguistic insights


Installation
Clone the repository and install dependencies:

git clone https://github.com/Thoshani/Infosys_Springboard/blob/main/Milestone1/finalproject.ipynb

cd finalproject

pip install -r requirements.txt

If requirements.txt is missing, install manually:

pip install transformers sentence-transformers scikit-learn matplotlib


Usage
Open the notebook:

   jupyter notebook FINAL.ipynb

Run the cells in order
Provide your own text files or use the sample ones
View generated summaries, paraphrases, similarity metrics, and visualizations

Example Workflow
Here's a typical pipeline run:

Input Text: A paragraph or full document
Summarization:

T5 generates a short, concise summary
BART creates a structured summary
PEGASUS produces an abstractive summary


Paraphrasing: Each summary is rewritten differently
Similarity Scoring: Compare summaries and paraphrases with original text
Visualization: Bar charts for length and similarity, plus bigram charts for frequent patterns

Outputs

The project generates several types of outputs:

Summaries: Multiple model outputs for the same input
Paraphrases: Alternative phrasings of summaries
Metrics: Length of summaries and cosine similarity with original text
Plots: Model comparison bar charts and bigram visualizations

