# RAG-App

This is a Retreival Augmented Generation app made using streamlit, langchain and Flask libraries. It allows users to upload multiple PDFs to do question-asnwering using Large Language Models(LLM). The uploaded PDFs are first converted into embeddings and stored in vector database like Pinecone. When the user asks a question, the question along with the user question is sent to the LLM to convert the question into a standalone question based on the chat history. Afterwards, a vector similarity search is done using the standlone question against the vector database to retrieve relevant chunks from the uploaded PDFs. The documents along with the standalone question is sent to the LLM for the final answer. By retrieving relevant documents or chunks of text, the LLM has more context for answering the question. Finally, the model output and the releavant documents used as context are sent to the frontend. By showing the which documents were used for generating, we can increase transperancy and explainability in LLM apps.

Tha app.py file contains the backend logic, qa_chain.py declares the function for the question-answering chain made using langchain and ui.py containes the code for frontend.

Commands for running the backend server: python3 app.py for starting the backend server

Commands for running the frontend : streamlit run ui.py --server.enableXsrfProtection=false
