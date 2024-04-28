# How to build DocuQuery chatbot to chat with your own data with Flowise and Pinecone Vector database?

## Prerequisites:
1. Open AI API key
2. Pinecone API key and Pinecone Index name
   - To create a Pinecone index first create an account then select index, give a name for the index and the dimension (e.g., 1536)

## Procedure Steps to build a rag chatbot to chat with your own data

### Task-1: Setting Up
Open command prompt or Terminal
1. Install flowise using npm:
 npm install -g flowise
2. Start Flowise:
npx flowise start
3. Open [http://localhost:3000](http://localhost:3000) in your web browser.

### Task-2: Create a New Chatflow in flowise
1. Click on the '+' button on the top right corner of the page to create a new chatflow and give it a name, for example, 'project-1'.
2. Drag and Drop the following from the left side menu:
- Add PDF file from the Document Loader section under LangChain.
- Add OpenAI from the chat models section.
- Add RecursiveCharacterText Splitter from the text splitter section.
- Add Pinecone upsert vector DB from the vector stores section.
- Add OpenAI embeddings from the embeddings section.
- Add conversational retrieval QA chain from the LLM Chains section.
- Add in-memory cache to the chat OpenAI input cache.

### Task-3: Provide API Keys
Provide API keys for the OpenAI model and Pinecone database. Also, provide the name of the model for the embedding model that is being used.

### Task-4: Connect Components
Connect each component to another as follows:
- Connect the PDF file to the recursive character text splitter to split the document into chunks.
- Connect the output of the PDF to the inputs of the Pinecone vector store.
- Connect OpenAI embeddings to the inputs of the Pinecone vector store.
- Connect the output of the chat OpenAI and the output of Pinecone to the input of the conversational retrieval Q&A chain.

### Task-5: Save the Chatflow
Save the chatflow once all the components are connected and configured.
## Chatbot Deployment Guide

1. **Develop Your Chatbot**: 
   Implement the logic of your chatbot using a language model or framework.

2. **Create a Streamlit App**: 
   Write a Streamlit script (`app.py`) that integrates your chatbot and provides a user interface.

   ```bash
   streamlit run app.py
Test Locally:
Ensure functionality by running your app locally.
Prepare for Deployment:
Set up a requirements.txt for dependencies.
Create a Procfile for Heroku deployment.
Select a Hosting Service:
Choose a platform like Heroku or Streamlit Sharing.
Deploy Your App:
For Heroku: Use Git to deploy via Heroku CLI.
For Streamlit Sharing: Deploy directly through Streamlit.
Configure Your Deployment:
Set environment variables in your hosting service.
Ensure Security:
Confirm HTTPS deployment to secure data transmission.
Monitor and Maintain:
Keep an eye on performance and update as needed.

### TESTING
- **Objective:** To evaluate the performance of DocuQuery and ensure its functionality meets the intended requirements.
- **Test Cases:**
  1. **Document Upload Test:**
     - **Test Case:** Upload a Textbook of a subject or a cookbook recipe  PDF.
     - **Expected Result:** DocuQuery explains the topic of requested.
     - **Actual Result:** Key topics are successfully extracted and presented to the user.
  2. **Question-Answering Test:**
     - **Test Case:** Ask DocuQuery about the explanation of a topic.
     - **Expected Result:** DocuQuery accurately identifies the specific topic and provides relevant details.
     - **Actual Result:** DocuQuery retrieves the correct topic information from the uploaded documents.
  3. **Error Handling Test:**
     - **Test Case:** Input a vague query with ambiguous terms.
     - **Expected Result:** DocuQuery responds with a helpful error message, guiding the user to provide clearer input.
     - **Actual Result:** DocuQuery recognizes the ambiguity and prompts the user Hmm, I dont know.
     - ## Encountered Challenges and Solutions

### Document Extraction Inconsistencies
- **Challenge**: There were irregularities in the results from document extraction.
  - **Solution**: Enhancement of document parsing algorithms has been implemented, resulting in increased accuracy of data extraction.

### Response Time Lags
- **Challenge**: Users experienced occasional lags in receiving responses.
  - **Solution**: Backend processes have been optimized and server configurations adjusted, leading to quicker response times.

### Complex Query Misinterpretations
- **Challenge**: The system sometimes misinterpreted queries of a complex nature.
  - **Solution**: The training datasets have been expanded and the natural language processing models have been refined to better comprehend a wider array of query structures.

# Quality and Documentation for DocuQuery

## Quality Assessment

### User Experience
- **Report**: Users of DocuQuery find the platform's interface to be highly intuitive and user-friendly.
- **Impact**: The prompt and accurate responses provided by DocuQuery significantly enrich the document browsing and learning experience for users.

### Accuracy
- **Consistency**: DocuQuery maintains a high degree of precision in extracting and interpreting information from documents.
- **Outcome**: The system delivers relevant answers to user inquiries with a minimized rate of error, thereby reducing misinformation.

### Error Handling
- **Management**: DocuQuery efficiently manages errors, offering users clear and actionable feedback.
- **Guidance**: Upon receiving ambiguous queries, DocuQuery prompts users to rephrase their questions, ensuring a smooth and continuous user experience.






