**📌 Retrieval-Augmented Generation (RAG) Pipeline**

**🔍 Overview**
This project explores two approaches to building a **Retrieval-Augmented Generation (RAG) system**:
1. **Simple RAG Pipeline** - Utilizing vector stores for retrieval.
2. **Advanced RAG Pipeline** - Incorporating chains and a retriever for optimized query relevance.

---

**🛠️ 1. Simple RAG Pipeline (Vector Store-Based)**

**✅ What We Did:**
- **Document Ingestion** → Split large text into smaller chunks using `RecursiveCharacterTextSplitter`.
- **Vector Embeddings** → Converted text chunks into numerical representations via OpenAI embeddings.
- **Vector Store (Chroma)** → Stored the embeddings for fast retrieval.
- **Query Processing** → Retrieved top-k relevant chunks based on similarity search.
- **LLM Response Generation** → Passed retrieved chunks to an LLM for generating an answer.

**⚠️ Limitations:**
- **Basic retrieval** → Retrieves only based on similarity scores, possibly missing relevant info.
- **Truncation risk** → Long documents may get cut off due to model context limits.
- **No optimization for query relevance** → Some key information may be lost if its similarity score is low.

---

**🚀 2. Advanced RAG Pipeline (Using Chains & Retriever)**

To overcome the limitations of the simple RAG, we enhance it by introducing:

**🔗 Document Chain:**
- Structures retrieved chunks into a coherent format before passing them to the LLM.
- Ensures the model effectively utilizes context for improved responses.

**🛡 Retriever:**
- Enhances search beyond similarity-based ranking.
- Retrieves the most semantically relevant documents, even if their similarity score is low.
- Can combine different retrieval strategies (e.g., keyword, metadata filtering, hybrid search).

**🔄 Retrieval Chain:**
- Connects the **retriever** with the **document chain** to streamline the RAG pipeline.
- Takes user queries, retrieves optimal documents, and formats them for the LLM.
- Generates well-informed, contextually accurate responses.

---

**🎯 Why the Advanced Pipeline is Better?**
✅ **Better Query Relevance** → Retrieves more meaningful information compared to raw similarity search.
✅ **Improved Context Handling** → Chains help structure inputs, reducing loss of crucial data.
✅ **More Control Over Retrieval & Processing** → Enables fine-tuning based on different use cases.

By leveraging **retrieval chains and document chains**, this advanced pipeline significantly enhances **response accuracy, completeness, and contextual depth** compared to using vector stores alone. 🚀

