# RAG-based-QA-System
Data Collection / Crawling Fetches multiple Wikipedia pages using wikipediaapi. Document Creation Each page becomes a LangChain Document. Chunking Large documents are split into smaller overlapping chunks. Embedding Generation Each chunk is converted into vector form using all-MiniLM-L6-v2. Vector Storage Chunks a
What this pipeline is doing

Implementation

Data Collection / Crawling
Fetches multiple Wikipedia pages using wikipediaapi.
Document Creation
Each page becomes a LangChain Document.
Chunking
Large documents are split into smaller overlapping chunks.
Embedding Generation
Each chunk is converted into vector form using all-MiniLM-L6-v2.
Vector Storage
Chunks are stored in ChromaDB.
Retrieval
For a user query, the most relevant chunks are fetched.
Generation
Retrieved context is passed to the LLM (flan-t5-base) to generate the answer.
Why this is good for assignment

This version is good because it clearly demonstrates:

web crawling from Wikipedia
multiple reference pages
semantic search / vector retrieval
RAG question answering
use of LangChain
a workflow similar to the sample notebook

I implemented a Retrieval-Augmented Generation (RAG) based Question Answering system for the domain of Cricket. Multiple Wikipedia pages such as Cricket, Virat Kohli, MS Dhoni, Sachin Tendulkar, IPL, Test cricket, ODI, and T20I were crawled using the wikipediaapi Python library. The collected text was converted into LangChain documents and split into smaller overlapping chunks using RecursiveCharacterTextSplitter.

These chunks were embedded using the sentence-transformers/all-MiniLM-L6-v2 embedding model and stored in a Chroma vector database. When a user asks a question, the system retrieves the most semantically relevant chunks from the vector store and passes them, along with the user query, to a language model (google/flan-t5-base) for answer generation.

This approach improves answer relevance by grounding the generation process in retrieved external knowledge instead of relying only on the model’s internal memory.
