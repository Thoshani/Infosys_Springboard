Secure NLP Toolkit Platform: Summarization, Paraphrasing, and Authentication
This document details the architecture and deployment of the Secure NLP Toolkit, a comprehensive web application built on Streamlit, integrating state-of-the-art Hugging Face Transformers for core NLP functionalities and a secure JWT-based authentication system with an SQLite backend.

The platform is designed to provide robust text processing capabilities and includes a secure administrative layer for user management.

I. Core Application Features
A. Secure Authentication & Administration
Role-Based Access Control (RBAC): Supports distinct roles (Admin, General User) managed via an SQLite database.
Enhanced Security: Implements bcrypt for robust password hashing and JWT (JSON Web Tokens) for stateless, secure session management.
Password Recovery: Features a secure password reset protocol utilizing a time-bound OTP (One-Time Password) delivered via email.
Admin Dashboard: Provides a dedicated interface for administrators to monitor the user database and perform essential management tasks (user registration, deletion).
B. Natural Language Processing (NLP) Modules
Advanced Summarization: Utilizes production-ready Hugging Face models (Pegasus, FLAN-T5, BART) to generate abstractive and extractive summaries.
Evaluation: Includes quantitative performance metrics, specifically ROUGE scores, for comparing the generated summary against the original text.
Intelligent Paraphrasing: Offers text rewriting with granular control over output characteristics:
Complexity Control: Users can select complexity levels (Beginner, Intermediate, Advanced).
Stylistic Control: Supports various output styles (Formal, Academic, Creative, Simplification).
History & Analytics: Maintains a session-based history of recent NLP operations and provides basic metrics (word count, readability approximation).
II. Technical Specifications: Text Analysis Dashboard
The Text Analysis Dashboard serves as a dedicated utility within the platform to provide objective metrics and insights into the complexity and content of any input text. This functionality is powered primarily by the textstat and rake-nltk Python libraries, alongside standard NLTK components for tokenization.

A. Readability and Complexity Analysis
The application leverages the textstat library to calculate a range of industry-standard readability scores. These metrics are crucial for assessing the educational grade level required to comprehend the text:

Flesch Reading Ease (FRE): Provides a score from 0 to 100, where higher scores indicate text that is easier to read.
Flesch-Kincaid Grade Level (FKGL): Outputs a U.S. school grade level, indicating the educational attainment required to understand the text.
SMOG Index and Gunning Fog Index: Other grade-level estimates used for assessing textual difficulty.
The dashboard utilizes the FKGL score to categorize the text into Beginner, Intermediate, or Advanced complexity levels, providing a quick visual assessment.

B. Core Text Metrics and Keyword Extraction
The dashboard displays fundamental metrics derived using NLTK tokenizers and advanced algorithms:

Quantitative Metrics: Presents objective measures including Word Count, Sentence Count, Average Sentence Length, and a calculated Hard Word Count (words with 3+ vowels).
Keyword Extraction: The platform incorporates the Rapid Automatic Keyword Extraction (RAKE) algorithm via the rake-nltk library. This method identifies and presents a ranked list of the top keywords/key phrases by analyzing word frequency and co-occurrence within the text.
III. Deployment and Configuration Guide
A. Prerequisites
The deployment environment requires the following:

Python 3.8 or higher.
A valid ngrok authentication token to establish external network access for the Streamlit application.
A configured SMTP service (e.g., Gmail App Password) for the OTP email functionality.
B. Initial Setup and Credential Configuration
Before execution, critical security parameters within the source code must be updated. This is mandatory for a functional and secure deployment.

ngrok Token: Replace the placeholder in Cell 1 of the notebook:

NGROK_AUTH_TOKEN = "enter your auth_token" #<---Replace with your actual auth_token
Authentication Backend (Cell 3): Update the JSON Web Token (JWT) secret key and the SMTP credentials for the password reset function:

SECRET_KEY = "your-long-and-very-secret-key-for-jwt-goes-here" #<---Replace with a strong, complex secret key

# Inside the send_otp_email function
sender_email = "your mail id"  # <-- Replace with the authorized sending email address
sender_password = "password "  # <-- Replace with the corresponding application-specific password (Recommended)
Note on Email Security: The use of an App Password for services like Gmail is strongly recommended over the main account password for security integrity.

C. Execution
The application is designed for sequential execution within the provided Jupyter Notebook (Code(Milestone_3).ipynb).

Execute Cells 1 through 7 sequentially to install dependencies, compile the app.py file, define backend logic, and initialize the secure user database.
Execute the final cell (Cell 8) to initiate the application:
The Streamlit service will launch in the background.
The large transformer models will be loaded (requires up to 60 seconds).
The ngrok tunnel will be established, and the public access URL will be printed to the console.
D. Initial Administrative Access
Upon initialization, the database automatically provisions a default administrator account:

Role	Email	Password
Admin	admin@ai	Infosys
This account should be utilized for initial login and subsequent user management operations within the Admin Dashboard.

IV. Platform Demonstration
A recorded demonstration showcasing the platform's key features, including the secure login process, summarization module, and administrative functions, is available via the link below:

[https://screenrec.com/share/DO5gsMVpyl]

V. Technical Stack Summary
Component	Technology/Library	Function
User Interface	Streamlit	Front-end framework for rapid application development.
Authentication	bcrypt, PyJWT, SQLite3	Password hashing, session token management, and database storage.
Core NLP	Hugging Face transformers	Implementation of models (Pegasus, BART, FLAN-T5) for summarization/paraphrasing.
Text Analysis	textstat, rake-nltk	Readability calculation and automated keyword extraction.
Evaluation	rouge_score	Standard metric for quantitative assessment of generated summaries.
