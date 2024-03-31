
Task 1: Question and Answering system
=======================================

Description
-----------
A client asked us to enhance our chatbot in order to be able to answer questions from a large PDF they provided. We successfully split the document into paragraphs and created a few questions for each of them to test. However, we faced challenges in proceeding forward, so we decided to seek assistance to figure out how to use these questions to match the relevant paragraph for answering.

The task is to use the questions provided and identify the most relevant paragraph for each question, essentially performing a similarity task.

Files
-----
Dataset: similarity.csv
- Contains one column for paragraphs.
- Separate columns prefixed with "Question", each corresponding to a question that should match the paragraph in the same row.

Deliverables
------------
- A notebook with your solution.
- A sheet with predicted answers for the test data.

Answer the following questions in the README:
----------------------------------------------
1. What were the main challenges you faced, and how did you address them given the limited time?
   - No ground truth data to use for evaluation:
     - I applied multiple models to select the top 10 ranked answers to try to use it as ground truth after a renaking based on the 6 models with answer frequesncy
     , inspired by part of the paper "Ranking Large Language Models without Ground Truth."
     - Attempted to use elastic search for evaluation, but time constraints prevented its implementation.
   - Null questions in the Dataset:
     - I used ChatGPT3.5 to generate questions in Egyptian dialect manually, without using an API due to time constraints.

2. In your opinion, what is the best approach to handle question answering from a document?
    if it from pdf:
        - Use pretrained OCR to extract text and information.
        - Create embeddings of the text to represent the document data (sentence embeddings).
        - Embed the query and search for similarity among the document embeddings.
        - Use the advantages of large language models (LLMs) for enhanced answering and evaluate the model.

