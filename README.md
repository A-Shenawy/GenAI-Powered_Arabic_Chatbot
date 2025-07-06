![E-Commerce AI Pipeline in Arabic](https://raw.githubusercontent.com/A-Shenawy/GenAI-Powered_Arabic_Chatbot/main/E-Commerce%20AI%20Pipeline%20in%20Arabic.png)

# A GenAI-Powered Arabic Chatbot for E-Commerce Customer Service

This repository contains the code, data, and documentation for implementing a modular, Arabic-language, Retrieval-Augmented Generation (RAG) chatbot tailored to e‑commerce customer support. It encompasses the full pipeline from data scraping and cleaning to embedding, indexing, and real-time interaction in a Streamlit-based interface.

---

## 🚀 Table of Contents

* [Abstract](#abstract)
* [Features](#features)
* [Repository Structure](#repository-structure)
* [Installation](#installation)
* [Usage](#usage)
* [Reproducing Results](#reproducing-results)
* [Evaluation](#evaluation)
* [Contributing](#contributing)
* [License](#license)
* [References](#references)

---

## 📄 Abstract

Leverages AraBERT and OpenAI embeddings within a RAG framework to deliver contextually accurate, low-latency Arabic responses for e‑commerce queries via a Streamlit UI. The system scrapes, cleans, normalizes, embeds, and indexes Arabic product data, enabling seamless question-answering tailored to Arabic-speaking customers.

---

## ✨ Features

* 📥 **Data Scraping**: Automated headless browser scraping of dynamic Arabic e‑commerce pages
* 🧹 **Text Cleaning**: Diacritics removal, punctuation stripping, stopword filtering, and lemmatization
* 🔍 **Embedding & Indexing**: AraBERT + OpenAI embeddings stored in Qdrant for fast semantic search
* 🤖 **RAG Module**: Retrieval of top‑k items and dynamic prompt construction for LLM generation
* 🖥️ **Streamlit UI**: Interactive chat interface with history, native Arabic layout, and real‑time responses

---

## 📂 Repository Structure

```plaintext
├── data/                  # Raw and cleaned data dumps
├── notebooks/             # Jupyter notebooks for experiments and evaluation
├── src/                   # Core modules (scraper, cleaner, embedder, indexer, rag, ui)
│   ├── scraper.py
│   ├── cleaner.py
│   ├── embedder.py
│   ├── indexer.py
│   ├── rag.py
│   └── app.py             # Streamlit application entry point
├── requirements.txt       # Python dependencies
├── README.md              # This file
└── LICENSE
```

---

## ⚙️ Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/your-username/arabic-ecom-chatbot.git
   cd arabic-ecom-chatbot
   ```

2. **Create a virtual environment**

   ```bash
   python3 -m venv venv
   source venv/bin/activate  # on Windows: venv\Scripts\activate
   ```

3. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```

4. **Configure environment variables**

   Create a `.env` file with your OpenAI and Qdrant credentials:

   ```dotenv
   OPENAI_API_KEY=your_openai_key
   QDRANT_URL=http://localhost:6333
   QDRANT_API_KEY=your_qdrant_key  # if applicable
   ```

---

## 🏃‍♀️ Usage

1. **Run the scraper**

   ```bash
   python src/scraper.py --output data/raw_products.json
   ```

2. **Clean and normalize text**

   ```bash
   python src/cleaner.py --input data/raw_products.json --output data/cleaned_products.json
   ```

3. **Generate and upload embeddings**

   ```bash
   python src/embedder.py --input data/cleaned_products.json --collection products
   ```

4. **Launch the Streamlit app**

   ```bash
   streamlit run src/app.py
   ```

---

## 🔄 Reproducing Results

To reproduce the qualitative evaluation results (Table 1), run the notebook:

```bash
jupyter notebook notebooks/evaluation.ipynb
```

---

## 📊 Evaluation

Results from a manual qualitative evaluation on 24 queries:

| Category | Count |
| -------- | ----- |
| Correct  | 18    |
| Relevant | 3     |
| Partial  | 2     |
| Wrong    | 1     |

---

## 🤝 Contributing

Contributions are welcome! Please open an issue or submit a pull request to improve features, fix bugs, or expand documentation.

---

## 📜 License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

---

## 📚 References

1. Kalva, R. et al. "Optimizing E-commerce Platforms with GenAI-Driven DevOps and LLMOps." *Journal of AI, ML & Data Science*, 2024.
2. Lewis, P. et al. "Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks." arXiv:2005.11401v4, 2021.
