# **Secure NLP Toolkit Platform: Summarization, Paraphrasing, and Authentication**

This document details the **architecture and deployment** of the **Secure NLP Toolkit**, a comprehensive web application built on **Streamlit**, integrating **Hugging Face Transformers** for core NLP functionalities and a **secure JWT-based authentication system** with an **SQLite backend**.

The platform provides robust text processing capabilities and includes a **secure administrative layer** for user management.

---

## **I. Core Application Features**

### **A. Secure Authentication & Administration**

* **Role-Based Access Control (RBAC):**
  Supports distinct roles — **Admin** and **General User** — managed via an **SQLite database**.

* **Enhanced Security:**
  Implements **bcrypt** for password hashing and **JWT (JSON Web Tokens)** for stateless, secure session management.

* **Password Recovery:**
  Includes a **secure password reset** protocol utilizing a **time-bound OTP (One-Time Password)** delivered via email.

* **Admin Dashboard:**
  Offers a dedicated interface for administrators to:

  * Monitor the user database
  * Register or delete users
  * Manage overall system access

---

### **B. Natural Language Processing (NLP) Modules**

* **Advanced Summarization:**
  Powered by **Hugging Face models** such as:

  * **Pegasus**
  * **FLAN-T5**
  * **BART**
    Supports both **abstractive** and **extractive** summarization.

* **Evaluation Metrics:**
  Implements **ROUGE scores** to quantitatively compare generated summaries with the original text.

* **Intelligent Paraphrasing:**
  Enables text rewriting with granular controls:

  * **Complexity Control:** Beginner / Intermediate / Advanced
  * **Stylistic Control:** Formal / Academic / Creative / Simplified

* **History & Analytics:**
  Tracks session-based NLP operations, including:

  * Word count
  * Readability approximation
  * Recently processed text summaries

---

## **II. Technical Specifications: Text Analysis Dashboard**

The **Text Analysis Dashboard** provides insights into the **complexity, readability, and structure** of any given text using **textstat** and **rake-nltk** libraries.

---

### **A. Readability and Complexity Analysis**

Uses the `textstat` library to compute industry-standard readability scores:

* **Flesch Reading Ease (FRE):**
  Scores range from **0–100**, where higher indicates easier readability.

* **Flesch-Kincaid Grade Level (FKGL):**
  Outputs a U.S. **school grade level** indicating the education required to comprehend the text.

* **SMOG Index & Gunning Fog Index:**
  Provide additional grade-level estimations of text difficulty.

* **Complexity Categorization:**
  Based on FKGL, the dashboard visually classifies text as:

  * **Beginner**
  * **Intermediate**
  * **Advanced**

---

### **B. Core Text Metrics and Keyword Extraction**

Derived using **NLTK** tokenizers and **RAKE** algorithms:

* **Quantitative Metrics:**

  * Word Count
  * Sentence Count
  * Average Sentence Length
  * Hard Word Count (words containing 3+ vowels)

* **Keyword Extraction:**
  Employs **RAKE (Rapid Automatic Keyword Extraction)** to:

  * Identify top keywords/key phrases
  * Rank them by frequency and contextual co-occurrence

---

## **III. Deployment and Configuration Guide**

### **A. Prerequisites**

Ensure the following before deployment:

* **Python 3.8+**
* **ngrok authentication token** (for public URL access)
* **SMTP service credentials** (e.g., Gmail App Password for OTP delivery)

---

### **B. Initial Setup and Credential Configuration**

Before running the notebook, update key configurations:

```python
# ngrok Authentication
NGROK_AUTH_TOKEN = "enter your auth_token"  # Replace with your actual token
```

```python
# JWT and SMTP Settings
SECRET_KEY = "your-long-and-very-secret-key-for-jwt-goes-here"

# Inside send_otp_email()
sender_email = "your_email@example.com"
sender_password = "your_app_specific_password"
```

> 💡 **Security Note:** Always use an **App Password** (not the main account password) for SMTP-based OTP functionality.

---

### **C. Execution Steps**

1. Open the notebook: **Code(Milestone_3).ipynb**
2. Run **Cells 1–7** sequentially to:

   * Install dependencies
   * Compile `app.py`
   * Initialize authentication & database setup
3. Run **Cell 8** to:

   * Launch the **Streamlit** app
   * Load transformer models (~60 seconds)
   * Establish **ngrok tunnel** and print the public URL

---

### **D. Initial Administrative Access**

A default admin account is auto-created during initialization:

| **Role** | **Email** | **Password** |
| -------- | --------- | ------------ |
| Admin    | admin@ai  | Infosys      |

Use this account for first login and to manage users in the **Admin Dashboard**.

---

## **IV. Platform Demonstration**

🎥 **Demo Link:**
[https://screenrec.com/share/DO5gsMVpyl](https://screenrec.com/share/DO5gsMVpyl)

The demonstration includes:

* Secure login flow
* Text summarization & paraphrasing modules
* Admin dashboard operations

---

## **V. Technical Stack Summary**

| **Component**      | **Technology/Library**    | **Function**                                          |
| ------------------ | ------------------------- | ----------------------------------------------------- |
| **User Interface** | Streamlit                 | Web-based front-end framework                         |
| **Authentication** | bcrypt, PyJWT, SQLite3    | Secure login, token management, and database          |
| **Core NLP**       | Hugging Face Transformers | Pegasus, FLAN-T5, BART for summarization/paraphrasing |
| **Text Analysis**  | textstat, rake-nltk       | Readability computation and keyword extraction        |
| **Evaluation**     | rouge_score               | Quantitative summary performance metrics              |




Would you like me to **generate this as a well-formatted PDF** with bold headings, bullet icons, and embedded diagrams (no cover page)? I can include light visuals for each section (e.g., a lock icon for authentication, graph for dashboard, etc.) and ensure perfect alignment for submission.
