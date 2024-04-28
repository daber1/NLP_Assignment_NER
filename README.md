# Student Info 
* Full name: Vladislav Lopatovskii
* Email: v.lopatovskii@innopolis.university
* Nickname in CodaLab: daber
* Link to the GitHub repository: https://github.com/daber1/NLP_Assignment_NER
# Report
## Overview
In this assignment, I was trying to develop a NER system for the Russian language. The goal was to accurately identify and classify named entities.
## Initial approach (The first solution)
Initially, I started by implementing a Conditional Random Field (CRF) model  with the use of spacy and sklearn_crfsuite libraries. This method involved tokenization of the text and feature extraction, followed by training the CRF model on labeled data.
I extracted the following features from each token:
* lowered text
* the last 3 symbols
* the last 2 symbols
* is the text uppercased
* is the text titled
* is the text digits
* PoS tag of the token
* the first two symbols of the PoS tag 
Also, I extracted info about the next token and the previous one if available.
## Results with CRF model
The initial solution demonstated promising performance, achieving 0.48 F1 score. This indicates reasonable accuracy in identifying named entities.
## Second approach
To potentially enhance performance further, I explored more advanced models for NER. I attempted to leverage BERT model.
## Challenges with BERT
I faced signficant challenges with integrating BERT in this task:
* Output Formattin: aligning BERT's token-level(sub words) predictions with original text for proper evalutation
* F1 Score Issues: Difficulties in formatting the output data resulted in low F1 scores close to 0, although for the validation dataset the model showed an F1 score of 0.88 
## Conclusion
Given the challenges encountered with BERT integration, I have decided to proceed with the CRF model. The simplictiy and effectiveness of the CRF model outweighed the complexities associated with BERT solution.