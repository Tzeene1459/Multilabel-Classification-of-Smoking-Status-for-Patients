# **Title: Smoking Status Identification from Clinical Notes**

## **Task:**

The primary objective of this project was to predict smoking status based on text data. I aimed to classify individuals into categories such as past smoker, current smoker, smoker, non-smoker, and unknown smoking status by applying natural language processing (NLP) and machine learning (ML) techniques.

## **Methodology:**

### XML File Parsing:
I began by parsing XML files containing text data. I extracted relevant XML elements to retrieve text sections for further processing.

### Data Preparation:
I employed three main types of features, including TF-IDF frequency vectors, Word2Vec embeddings, and ClinicalBERT embedding tensors.

**TF-IDF Frequency Vectors:**

I selected smoking-related sentences by extracting those explicitly mentioning smoking-related terms from the clinical notes.

Token generation involved processing the clinical text to create individual tokens representing words or phrases.

I handled negation by identifying phrases with negative expressions (e.g., "NOT") to ensure they were correctly interpreted, which was crucial for accurate classification.

The text data was preprocessed using tokenization, stop word removal, and punctuation removal.

I constructed a regular expression (regex) to match common terms and phrases associated with smoking and tobacco use, enabling selection of smoking-related sentences.

Features were extracted using TF-IDF (Term Frequency-Inverse Document Frequency) with unigram, bigram, and trigram representations.

Additional data cleaning included handling punctuation and irrelevant tokens.

I applied the TF-IDF vectorization process to both datasets and prepared the training and test datasets.

**Word2Vec:**

I used a pre-trained Word2Vec model built from Google News to calculate similarity scores between words in the notes and the word "smoking."

Words not present in the model were skipped to avoid errors.

I computed the average similarity score for each row and used it as a feature.

However, when I ran the logistic regression model on these features, it resulted in low accuracy, precision, and recall. Due to time constraints and the need for further feature enrichment, I decided not to include this model in the final results and focused on TF-IDF features instead.

**BERT:**

I fine-tuned the Bio_ClinicalBERT model to classify smoking status from clinical notes by leveraging its contextual embeddings.

The full clinical text was used to train the BERT embeddings.

The BERT model generated embedding tensors for the clinical notes.

However, I encountered an error while extracting model weights for five classes instead of two, preventing me from running a CNN on these tensors. Due to time constraints, I could not resolve this issue but successfully generated clinical embedding tensors from the BERT model.

### Machine Learning Models:

I implemented and evaluated several machine learning models, including:

Support Vector Machine (SVM): I applied a linear kernel and optimized it with feature scaling.

Naïve Bayes: I used pipelines combining TF-IDF vectorization.

Logistic Regression: Initially, I applied a multi-class logistic regression model, but it yielded suboptimal results.

I then incorporated bigrams and trigrams, which improved the model's performance.

The final results included comparisons between SVM and logistic regression, and based on the best results, I selected the logistic regression model as the final approach.

## **Evaluation Metrics:**
I evaluated the models using accuracy, precision, recall, F1-score, and confusion matrices.
Visualizations included heatmaps of confusion matrices to provide a detailed performance breakdown.

For a detailed walkthrough, check out the project slides attached comprising of the overall approach and results. 