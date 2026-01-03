# LLM Showcase – Retrieval-Augmented Generation Projects

This repository contains two **LLM-based showcase projects** demonstrating **Retrieval-Augmented Generation (RAG)** architectures.  
Both projects focus on combining **semantic retrieval** with **large language models** to generate context-aware, personalized responses.

The goal of this repository is to showcase **practical LLM engineering patterns** such as vector search, prompt augmentation, and domain-specific grounding.

---

## 👗 Fashion ChatBot – Domain-Specific RAG Chatbot

The **Fashion ChatBot** is a custom domain-specific chatbot focused on fashion trends.  
It enhances LLM responses by grounding them in retrieved textual context from curated datasets.

The project clearly demonstrates how **semantic retrieval and prompt augmentation** improve answer quality compared to vanilla LLM completions.

### ⚙️ Fashion ChatBot – Functional Breakdown

#### 1️⃣ Data Collection & Augmentation
- Loads a provided fashion trends dataset.
- Scrapes and integrates additional domain knowledge from Wikipedia  
  (e.g. *“2020s in fashion”*).
- Both sources are merged into a unified textual knowledge base.

**Purpose:**  
Create a richer and more realistic data foundation for domain-specific queries.

#### 2️⃣ Data Wrangling
- All text data is:
  - cleaned
  - normalized
  - stored in a structured DataFrame.
- Each row represents a semantic chunk of fashion-related information.

This prepares the data for embedding-based retrieval.

#### 3️⃣ Embedding Generation
- Text chunks are converted into vector embeddings using the **OpenAI Embeddings API**.
- Enables semantic similarity search instead of keyword matching.

**Result:**  
The chatbot understands *meaning*, not just exact wording.

#### 4️⃣ Semantic Retrieval
- User questions are embedded.
- Similarity is computed between the query and dataset embeddings.
- The most relevant text passages are selected as context.

This represents the **retrieval** step of a RAG pipeline.

#### 5️⃣ Prompt Augmentation & Answer Generation
- Retrieved context is injected into a custom prompt.
- The LLM generates answers grounded in retrieved information.
- Responses become:
  - more factual
  - more domain-specific
  - more consistent.

#### 6️⃣ Performance Comparison
For each example query:
- A **baseline response** is generated using a plain LLM completion.
- A **context-augmented response** is generated using retrieved data.

This highlights the benefits of RAG-based approaches.

#### 7️⃣ Interactive Chat Loop
- An interactive `while` loop allows continuous user queries.
- Each query triggers:
  - embedding
  - retrieval
  - prompt augmentation
  - response generation.

---

## 🏠 Home Match – Real Estate Recommendation System

**Home Match** implements an LLM-powered real estate recommendation workflow that processes natural language user preferences, compares them against existing property listings, and generates personalized recommendations.

### Core Functionality

- Generation of synthetic real estate listings  
- Storage of listings in a vector database  
- Collection and interpretation of user preferences  
- Semantic search for matching properties  
- Personalized descriptions and comparative evaluations  

### ⚙️ Home Match – Functional Breakdown

#### 1️⃣ Generating Real Estate Listings
- Synthetic real estate listings are generated (e.g. location, size, price, amenities).
- Listings are written in natural language to simulate realistic LLM interactions.
- These descriptions form the searchable knowledge base.

#### 2️⃣ Storing Listings in a Vector Database
- All listings are:
  - converted into embeddings
  - stored in a **LanceDB vector database**
- Enables **semantic similarity search** instead of keyword matching.

**Benefit:**  
Users can describe their preferences freely and still receive relevant results.

#### 3️⃣ Building the User Preference Interface
- User preferences are provided as natural language input  
  (e.g. *“A large family home with five bedrooms and a garden”*).
- Preferences are:
  - collected
  - interpreted
  - used as search queries for the vector database.

#### 4️⃣ Searching Based on Preferences
- User inputs are embedded.
- The vector database returns the most semantically similar listings.
- Top results are:
  - extracted
  - compared
  - analyzed (pros & cons).

#### 5️⃣ Personalizing Listing Descriptions
- A large language model (OpenAI API) is used to:
  - rephrase listings
  - tailor them to the user’s preferences.
- Output includes:
  - personalized recommendations
  - explanations of why a property fits or does not fit.

#### 6️⃣ Final Recommendation
- The system produces:
  - a final recommendation
  - including reasoning and justification.

---

## 🧰 Tech Stack

- **Python**
- **OpenAI API** (LLMs & embeddings)
- **LanceDB** (vector database)
- **Pandas / NumPy**
- **Wikipedia scraping**
- **Jupyter Notebooks**
