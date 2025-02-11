# 🔗 AI RAG

# Table Of Contents

- [Getting Started](#getting-started)
- [How to Run](#how-to-run)

## Getting started

### Simple RAG introduction https://huggingface.co/blog/ngxson/make-your-own-rag
- Let's create a simple RAG system that retrieves information from a predefined dataset and generates responses based on the retrieved knowledge.
- The system will comprise the following components:

![image](https://github.com/user-attachments/assets/f93b7b08-d20e-4bba-97d4-7724a6330803)





1. Embedding model: A pre-trained language model that converts input text into embeddings - vector representations that capture semantic meaning. These vectors will be used to search for relevant information in the dataset.
2. Vector database: A storage system for knowledge and its corresponding embedding vectors. While there are many vector database technologies like Qdrant, Pinecone, and pgvector, we'll implement a simple in-memory database from scratch.
3. Chatbot: A language model that generates responses based on retrieved knowledge. This can be any language model, such as Llama, Gemma, or GPT.


### Indexing phase
- The indexing phase is the first step in creating a RAG system. 
- It involves breaking the dataset (or documents) into small chunks and calculating a vector representation for each chunk that can be efficiently searched during generation.

![image](https://github.com/user-attachments/assets/40412309-562f-40da-9314-88b62578c417)




- The size of each chunk can vary depending on the dataset and the application. For example, in a document retrieval system, each chunk can be a paragraph or a sentence. In a dialogue system, each chunk can be a conversation turn.

- After the indexing phrase, each chunk with its corresponding embedding vector will be stored in the vector database. Here is an example of how the vector database might look like after indexing:


- To compare the similarity between two vectors, we can use cosine similarity, Euclidean distance, or other distance metrics. In this example, we will use cosine similarity. Here is the formula for cosine similarity between two vectors A and B:


### Retrieval phrase
- In the diagram below, we will take an example of a given Input Query from User. We then calculate the Query Vector to represent the query, and compare it against the vectors in the database to find the most relevant chunks.

![image](https://github.com/user-attachments/assets/7b0268b0-5b60-49f0-a99b-a597f402af53)




The result returned by The Vector Database will contains top N most relevant chunks to the query. These chunks will be used by the Chatbot to generate a response.




## How to Run
1. Clone this repo into the directory of your choice
   ```bash
   git clone https://github.com/JaneGuoS/customized_app_generator.git
   ```
2. Install pip install chromadb
   ```bash
     pip install --q chromadb
   ```
3. Install ollama
   ```bash
     pip install ollama
   ```
4. Run the sample
   ```bash
     python ai-rag.py 
   ```
     
