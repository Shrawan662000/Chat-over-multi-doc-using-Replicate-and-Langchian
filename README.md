# Chat-over-multi-doc-using-Replicate-and-Langchian

Here's a stepwise explanation of the procedure used in the code to build a chatbot for chat on multi-docs:
1. Setting Up the Environment:
•	Import necessary libraries: Streamlit, streamlit_chat, Langchain, os, dotenv, tempfile.
•	Load environment variables (if any) using load_dotenv().
2. Defining Chatbot Functions:
•	initialize_session_state(): Initializes session state to store chat history and responses.
•	conversation_chat(query, chain, history): Interacts with the conversational chain to generate a response to a query, considering chat history.
•	display_chat_history(chain): Displays the chat conversation using Streamlit's chat component.
•	create_conversational_chain(vector_store): Creates a conversational chain object, combining a large language model (LLM), retriever, and memory.
3. Main Application Logic:
•	main() function:
o	Initializes session state.
o	Sets up the Streamlit app interface.
o	Creates a sidebar for document uploads.
o	Handles document uploads:
	Extracts text from various file formats (PDF, DOCX, TXT).
	Splits text into chunks using CharacterTextSplitter.
	Generates embeddings for text chunks using HuggingFaceEmbeddings.  The Hugging Face model "sentence-transformers/all-MiniLM-L6-v2" is used for creating embeddings.
	Builds a vector store using FAISS for efficient retrieval.
o	Creates a conversational chain object.
o	Displays the chat interface.
4. Chatbot Interaction:
•	User uploads documents through the sidebar.
•	Documents are processed and indexed for retrieval.
•	User asks questions in the chat interface.
•	Chatbot retrieves relevant information from the indexed documents using the vector store.
•	LLM generates a response based on the retrieved information and chat history.
•	Response is displayed in the chat interface.
•	Chat history is maintained for context.
Key Points:
•	Langchain streamlines multi-document chatbot development.
•	LLM generates responses, vector store enables retrieval, and memory tracks conversation context.
•	Streamlit provides a user-friendly web interface.
