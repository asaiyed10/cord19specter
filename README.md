Paper

Direction 1: 

Goal: Ltierature Clustering 
-----------------------
Why: Identify trends in research within CORD-19 dataset

Methods: 
-------------------
1. CORD-19 Embedding 
    produced form SPECTER

2. PCA 
    N_compents that give explain 90% of underlying variation 

3. K-Mmeans
    Pass PCA compnents into K-means for cluster labeling 
    Determine K-Clusters by Silhoutte score

4. Visualization: 
    TSNE or UMAP on sample with Cluster assignments from K-MEANS
    


Direction 2: 

Goal: Colloboration Graph
-----------------------------
Why: What are the shortest distances between colloborators? 

Methods: 

author|author| source_paper| source_journal 

1. Create Co-authors graph 

2. BFS vs DFS search for Shortest-PAth between two authors 



Direction 3: 

Goal: Community Detection on Citation Graph 
--------------------------------
1. Preprocess citations from documents into edges 

author | citation | source_paper | cited_paper | source_journal| cited_journal| 


http://graphframes.github.io/graphframes/docs/_site/api/python/graphframes.examples.html#graphframes.examples.BeliefPropagation




Direction 4: 

Goal: Text Analysis describing clusters or communities 

Can we label each cluster or community? 














> ## Goal: 

    Problem: Search most covid related publications for information 

        Semantic search across article body and titles with simple UI 

            How?

            Something similar to this:

                https://www.kaggle.com/dirktheeng/anserini-bert-squad-for-semantic-corpus-search

            score and rank articles in a distributed way 

                When a search time comes in, multiple models may be used to score partitions across clusters and then rankings are reduced

        Also would be interesting:

            Distributed Citation Graph of articles in covid dataset 

                Clustering/Community Detection 

                Travel across Graph Visualization and pull corresponding article from DB

    Tools and Techniques:

        Finetune pretrained language model on Covid articles and titles in a distributed way across clusters

            Something similar to this http://sc20.supercomputing.org/proceedings/tech_poster/poster_files/rpost111s2-file3.pdf

            https://towardsdatascience.com/text-classification-in-spark-nlp-with-bert-and-universal-sentence-encoders-e644d618ca32

    Assumptions:

        The data is relatively clean and will require standard preprocessing (less than 5-6 hours of work) 

        Fine tuning a pre trained language model in a distributed way is not super expensive and well researched so there are tutorials and examples

        These are sophisticated tasks, but I am confident we should be able to tackle them in the timeframe given 
        
        
        
        


## Professor Feedback: 



    Once the system is in place what kinds of questions would like to answer?
    What insights could you generate for users?
    What could someone do with community detection on the citation network?
        Could you identify networks of research with high volume of research or many citations?
        Could this be helpful to someone who is trying to identify whose research to fund?
    If it is too hard to fine tune a pre-trained language model what is your backup plan?
