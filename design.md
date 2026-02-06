# Design Document – AI Syllabus Chatbot

## Overview
This project is an AI chatbot that helps students by answering questions based on syllabus PDFs. It uses a Retrieval-Augmented Generation (RAG) approach to make sure answers are accurate and syllabus-focused.

## System Architecture
The system is divided into simple components:
- A web interface where students ask questions
- A backend built using Node.js and Express
- A RAG pipeline implemented using LangChain
- A vector database (FAISS) to store syllabus embeddings
- A PDF data store for syllabus files
- Grok AI as the language model

## How the System Works
1. A student asks a question through the chat interface.
2. The backend receives the request and processes it.
3. Relevant syllabus content is searched from the vector database.
4. The retrieved content and user question are sent to the RAG engine.
5. Grok AI generates an answer using the provided syllabus context.
6. The final response is sent back to the student.

## Syllabus Data Ingestion
- Admin uploads syllabus PDF files.
- Text is extracted and divided into smaller chunks.
- Embeddings are created and stored in the vector database.
- This process happens periodically and not during live queries.

## Key Design Choices
- RAG is used to avoid incorrect or out-of-syllabus answers.
- All external API calls are handled by the backend for security.
- Chat sessions are not stored to keep the system simple.
- The system follows a synchronous request-response flow.

## Future Improvements
- Deployment on AWS cloud.
- Support for multiple courses and institutions.
- Improved admin dashboard and monitoring.
