# Bert-Question-Answering
 
### Aim
- To build a Question Answering Model to find answers from large text documents📖

### Use case
- Large documents like legal document contains number of clauses which makes reading through the whole document and understanding tough for a human. This model aims to assist humans with their queries from such large documents thereby saving time and effort.

###### *This is a an attempt to reproduce my previous work. Due to data privacy reasons I have taken a more generic approach here*

### Tools used
- 1. PDFminer  
- 2. TFIDF and Spacy
- 3. bert-base-uncased trained on [SQuAD2.0]([url](https://rajpurkar.github.io/SQuAD-explorer/explore/v2.0/dev/)) Dataset. 

### Approach
- **PDFminer** : is used to mine text from pdfs. In case of scanned documents OCR tools like [TesserOCR](https://anaconda.org/conda-forge/tesserocr) can be used. 
- **Similarity** :Spacy similarity is used to find the top 100 paragraphs that is similar to our question. This help is filtering out irrelavant paragraphs. Another similarity method that is tested here is TFIDF and cosine similarity. Paragraphs with high similarity with the question are more likely to contain the relevant answer. 
- **Bert** : trained on SQuAD dataset from Hugging face transformer is used in this scenario. We can also fine-tune our model in the custom-dataset if available for domain adaptation. Topk parameter can be changed to find top 'k' number of answers along with their confidence score. The model also outputs the start logit and the end logits which can be used to backtrack into the original paragraph in the PDF. We can further go and highlight the answers in the original pdf using PDF plumber. Though I have not added that part of the code this time. 

### Future Improvements
- 1. A better similarity technique like ELMO or doc2vec scores can be used to find the similarity in case of longer sequences and pargraphs.
- 2. A better model like longformer can be used since it handles longer sequences better than bert. Bert has a sequence length limit of 512, which does not process the whole information at once. Since clauses are generally short I have chosen to go ahead with Bert in this scenario. 







*I will update the repo with training code and deployment method followed in future*.
<<<<<<< Updated upstream
=======
 
>>>>>>> Stashed changes
