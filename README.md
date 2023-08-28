# Sentence-Level-Summ
 Sentence-Level Extractive Text Summarisation on WikiHow Data    
 <p align="justify">This repository stores the relevant files for NTU 2021/2022 Sem 2 AI6127 Deep Neural Networks for Natural Language Processing course group project. Great appreciation for all the other team members' hard work.   </p>
 
 ### Model Structure
 
![Model structure](https://github.com/zhangziyi1996/Sentence-Level-Summ/assets/143377198/bbfa45e8-52af-4b43-8edf-7436a0203976)      
<p align="justify">The overall model structure is shown as above, where the core part is the bottom pre-trained sentence embedding transformer from HuggingFace.     
Specifically, two sentence-level encoders **all-MiniLM-L6-v2** & **all-distilroberta-v1** are used in this project and their empirical performances are compared side by side.   </p> 

### Model Details
• Pre-trained Model: all-MiniLM-L6-v2 / all-distilroberta-v1   
• Input Dimension: 384 / 768   
• Hidden Layer Dimension: 256   
• Number of Encoder Layers: 3   
• Number of Attention Heads: 4   

### Dataset Introduction
<p align="justify">In 2018, the WikiHow dataset was completed and hosted as a public dataset as a solution to the lack of publicly-available large-scale quality text summarization datasets. Different from the other commonly used summarization datasets such as New York Times, CNN/Daily Mail and etc., WikiHow contains articles written by mostly ordinary people. This non-professional style prevents 
the ubiquitous Inverted Pyramid writing style in news articles , which leads to an abnormally high score of the naive lead-3 summarization method. The dataset was constructed by extracting articles from WikiHow website and in total comprises of 230,843 articles and respective summary pairs.</p>

### Training Details
<p align="justify">Due to the size of the WikiHow dataset, we have trimmed it to only contain paragraphs with a maximum of 80 sentences. This still contains 150,000 training pairs which is 90% of the original
dataset. We then trained the model for 10 epochs, in each epoch, a random sample of 20,000 training pair samples are selected from the trimmed dataset.</p>

### Evaluation Results
Other than the proposed model, other comparison baselines used are:   
• TextRank [1]    
• MatchSum model proposed in the paper: "Extractive Summarization as Text Matching" [2]      
• HiBERT model proposed in the paper: "HIBERT: Document Level Pre-training of Hierarchical Bidirectional Transformers for
Document Summarization" [3]     
The final evaluation result is shown in the table below: (PTX-Sum is our proposed model name)
![result11](https://github.com/zhangziyi1996/Sentence-Level-Summ/assets/143377198/f41c476f-9eb5-4560-85c3-c16195c9f9a4)

As what can be seen in the table, our proposed model which uses all-MiniLM-L6-v2 as sentence-level encoder achieves the best result.
### References
<p align="justify">[1]R. Mihalcea and P. Tarau. “TextRank: Bringing Order into Texts”. In: Proceedings of
EMNLP-04and the 2004 Conference on Empirical Methods in Natural Language Processing.
Barcelonaand Spain, July 2004.   </p>
<p align="justify">[2]Ming Zhong et al. “Extractive Summarization as Text Matching”. In: CoRR abs/2004.08795
(2020). arXiv: 2004.08795. URL: https://arxiv.org/abs/2004.08795.   </p>
<p align="justify">[3]Xingxing Zhang, Furu Wei, and Ming Zhou. “HIBERT: Document Level Pre-training of Hierarchical
Bidirectional Transformers for Document Summarization”. In: Proceedings of the
57th Annual Meeting of the Association for Computational Linguistics. Florence, Italy: Association
for Computational Linguistics, July 2019, pp. 5059–5069. DOI: 10.18653/v1/P19-
1499. URL: https://aclanthology.org/P19-1499.    </p>

