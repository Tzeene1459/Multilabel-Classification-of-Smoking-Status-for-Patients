# Smoking Status Identification from Clinical Notes  

## Project Overview  
This project aims to classify individuals' smoking status based on clinical text data. Using natural language processing (NLP) techniques and machine learning models, the system categorizes patients into five groups:  

- **Current Smoker**  : A patient that is denoted as someone who currently smokes any amount of tobacco through any means
- **Past Smoker**  :  A patient that is classified as someone who was a smoker in any capacity in the past but doesn't currently smoke. 
- **Smoker (unspecified)**  : A patient that has some kind of smoking history but it isn't clear whether they smoke currently or have smoked in the past.
- **Non-Smoker**  : A patient that doesn't smoke currently, and has never smoked in the past.
- **Unknown Smoking Status**  : Discharge notes don't contain any information related to smoking. 



## Data 

The data for this project was acquired from this challenge by Harvard Medical School: https://portal.dbmi.hms.harvard.edu/projects/n2c2-2006/ The data can be downloaded after registering/signing in to their portal on the same link. 

The data overall contained the de-identified discharge summaries/clinical notes from 889 patients in XML format. The data was completely unstructured, one XML file per patient discharge summary. The data was annotated, with the patient smoking status stated in the head of the XML document. 

Annotated Training Samples Examples:

1. "She is a past smoker, but quit two years ago when she was found to have right upper lobe nodule, which was resected and found to be positive for TB granuloma, for which she was treated with antibiotics for nine months". -- Past Smoker
2. "She quit smoking four months ago." -- Current Smoker
3. "Depression, anxiety, chronic obstructive pulmonary disease/asthma, history of tobacco abuse, chronic headaches, atypical chest pain with 6/97 Dobutamine MIBI revealing no ischemia and a history of tuberculosis exposure." -- Smoker
4. "No tobacco." -- Non-Smoker
5. "Most recently, she developed dyspnea two days prior to admission, trigger was felt to be marijuana smoke in the building where she lives where there are many drug dealers." -- Unknown

The dataset was available pre-segregated into training samples and a test set.  

## Repository Structure  


smoking-status/ 

│-- ProjectReport.md # Detailed report of the project methodology and findings

│-- README.md # Project documentation

│-- SmokingStatusBERT.ipynb # Notebook for BERT-based classification'

│-- SmokingStatusClassificationSIMPLE.ipynb # Notebook for SVM & Logistic Regression with TF-IDF

│-- SmokingStatusW2V.ipynb # Notebook for Word2Vec embeddings and experimentation

│-- SmokingStatusPresentation.pptx # Presentation summarizing project findings


## Installation & Setup  
To run the notebooks, you will need Python and the required libraries installed.  

**Clone the repository:**  
   
   git clone https://github.com/Tzeene1459/smoking-status.git
   cd smoking-status

**Running the Notebooks:**

    I used Google Colab for this project, so for least effort, you can consider running these notebooks in your colab, dependencies and required packages will install seamlessly in your colab environment, after downloading the datasets and replacing the data path variables to wherever you store the data locally. 

## Methodology

1. Data Parsing & Preprocessing
2. Feature Engineering
3. Model Training & Evaluation

## Results 

- TF-IDF with Logistic Regression outperformed other approaches
- Word2Vec yielded poor results and was not included in the final analysis
- BERT embeddings were generated, but classification could not be completed due to deadlines 

Selected Logistic Regression as the final model based on performance. Best Performance achieved was **77% Accuracy** using Naive Bayes. However, better results were seen in combination for all classes with LR.  

## Usage

- Run SmokingStatusClassificationSIMPLE.ipynb for TF-IDF-based classification
- Run SmokingStatusBERT.ipynb for BERT embeddings (fine-tuning pending)
- SmokingStatusW2V.ipynb contains Word2Vec experiments

## Challenges & Future Work

- Fixing BERT classification: Debug model weight extraction for multi-class classification
- Feature Engineering: Explore additional text representations and embeddings
- Expanding Dataset: Test on a more extensive and diverse dataset for generalizability. Some classes performed terribly due to poor support (3 records only for one of the classes)
- Class Imbalance: Address class embalance using a normalization technique or a synthetic data generation approach. 

## Link to Video Walkthrough 

-- will be available soon. :) 

## Author 

Tazeen Shaukat

