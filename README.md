COMPARATIVE ANALYSIS OF RAG TECHNIQUES AND LLM MODELS FOR PERSONALIZED NEWS SUMMARIZATION
Abstract

The exponential growth of digital news content has created challenges for users in consuming and understanding large volumes of information efficiently. Personalized news summarization aims to provide concise and relevant summaries based on user interests and queries. This project presents a comparative analysis of Retrieval-Augmented Generation (RAG) techniques and Large Language Models (LLMs) for personalized news summarization. Three retrieval approaches, namely Dense Retrieval, Hybrid Retrieval, and Fusion Retrieval, are evaluated using GPT, Llama, and Qwen language models. The system retrieves relevant news articles, generates summaries, and evaluates performance using ROUGE and BERTScore metrics. Experimental results demonstrate the effectiveness of combining advanced retrieval mechanisms with modern language models to improve summary quality and contextual relevance.

1. Introduction

With the increasing availability of online news articles, users often struggle to process large amounts of information. Automatic text summarization helps reduce reading time while retaining essential information. However, traditional summarization methods often lack personalization and contextual understanding.

Retrieval-Augmented Generation (RAG) addresses these limitations by retrieving relevant documents before generating summaries. By providing external knowledge to language models, RAG improves factual accuracy and contextual relevance. This project investigates the impact of different retrieval strategies and language models on personalized news summarization performance.

2. Dataset

The project utilizes the CNN/DailyMail dataset, a widely used benchmark for text summarization research.

Dataset Characteristics
Large collection of news articles
Human-written reference summaries
Multiple news categories
Suitable for summarization and retrieval evaluation
Preprocessing Steps
Removal of unwanted characters
Text normalization
Document chunking
Tokenization
Embedding generation
3. Methodology

The proposed methodology consists of the following phases:

Phase 1: Data Collection

News articles are loaded from the CNN/DailyMail dataset.

Phase 2: Data Preprocessing

Articles are cleaned, normalized, and divided into smaller chunks for efficient retrieval.

Phase 3: Embedding Generation

Sentence Transformer models generate dense vector embeddings for all document chunks.

Phase 4: Retrieval

Relevant documents are retrieved using:

Dense Retrieval
Hybrid Retrieval
Fusion Retrieval
Phase 5: Summary Generation

Retrieved documents are passed to selected LLMs (GPT, Llama, or Qwen) to generate summaries.

Phase 6: Evaluation

Generated summaries are evaluated using standard metrics.

4. RAG Techniques
4.1 Dense Retrieval

Dense Retrieval uses vector embeddings and semantic similarity search. It captures contextual meaning and retrieves semantically related documents even when exact keywords are absent.

Advantages:

Strong semantic understanding
Effective contextual retrieval

Limitations:

Computationally expensive
Requires embedding generation
4.2 Hybrid Retrieval

Hybrid Retrieval combines dense semantic search with keyword-based retrieval methods.

Advantages:

Improved retrieval accuracy
Better handling of rare keywords
Balanced retrieval performance
4.3 Fusion Retrieval

Fusion Retrieval combines outputs from multiple retrieval systems using score aggregation techniques.

Advantages:

Increased diversity of retrieved documents
Better overall relevance
Improved robustness
5. Large Language Models
