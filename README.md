# Identifying Research Trends with Literature Clustering of CORD-19 Specter Embeddings
### Authors: Ahson Saiyed Christle Iroezi

## Table of Contents


Clustering
-------------------
1. CORD-19 Embedding 
    produced form SPECTER
2. PCA n_components that give explain 90% of underlying variation
    
    > [exploratory_analysis/read_EMBEDDING_PCA_KMEANS_clean.ipynb](exploratory_analysis/read_EMBEDDING_PCA_KMEANS_clean.ipynb)
    
2. KMeans + Silhoutte Score + TSNE

    >[exploratory_analysis/kmeans_TSNE_sample_silhoutte_30_kmeans.ipynb](exploratory_analysis/kmeans_TSNE_sample_silhoutte_30_kmeans.ipynb)

3. Text Analysis of Cluster
    > [exploratory_analysis/kmeans_cluster_text_analysis_cluster_8.ipynb](exploratory_analysis/kmeans_cluster_text_analysis_cluster_8.ipynb)
    
    > [exploratory_analysis/kmeans_cluster_text_analysis_cluster_12.ipynb](exploratory_analysis/kmeans_cluster_text_analysis_cluster_12.ipynb)
    
    > [exploratory_analysis/kmeans_cluster_text_analysis_cluster_10.ipynb](exploratory_analysis/kmeans_cluster_text_analysis_cluster_10.ipynb)





Clustering Experimental
--------------
1. UMAP + HDBSCAN
    > [exploratory_analysis/other_instance/umap.ipynb](exploratory_analysis/other_instance/umap.ipynb)

    
    
    



Graphs
--------------------
1. Co-authorship Edgelist

    > [exploratory_analysis/build_graphs/build_coauthorship_edgelist.ipynb](exploratory_analysis/build_graphs/build_coauthorship_edgelist.ipynb)


2. Citation Edgelist 

    Preprocessing of raw document_parses citation data from pmc.json files , and create edgelist; upload to s3

    > [exploratory_analysis/other_instance/parse_documents_citations_clean.ipynb](exploratory_analysis/other_instance/parse_documents_citations_clean.ipynb)
    
    Pull edgelist from s3 for downstream tasks
    
    > [exploratory_analysis/build_graphs/build_citation_graph](exploratory_analysis/build_graphs/build_citation_graph.ipynb)

    












-------------------------------------------------
-------------------------------------------------

# Exploratory Analysis 
On metadata.csv -- perform exploratory analysis? 
    How many documents exists? 
    How many unique journals? 
    Plots that show distribution

# Motivation: 

# Direction 1: 

Goal: Literature Clustering 
-----------------------
Why: Identify trends in research within CORD-19 dataset

Methods: 
-------------------
1. CORD-19 Embedding 
    produced form SPECTER

2. PCA 
    n_components that give explain 90% of underlying variation 

3. K-Mmeans
    Pass PCA components into K-means for cluster labeling 
    
    Determine K-Clusters by Silhoutte score

4. Visualization: 
    TSNE or UMAP on sample with Cluster assignments from K-MEANS
    
5. Text Analysis describing clusters

   Can we label each cluster? 
    


# Direction 2: 

Goal: Colloboration Graph
-----------------------------
Why: What are the shortest distances between colloborators? 

Methods: 

author|author| source_paper| source_journal 

1. Create Co-authors graph 

2. BFS vs DFS search for Shortest-PAth between two authors 



# Direction 3: 

Goal: Community Detection on Citation Graph 
--------------------------------
1. Preprocess citations from documents into edges 

author | citation | source_paper | cited_paper | source_journal| cited_journal| 


http://graphframes.github.io/graphframes/docs/_site/api/python/graphframes.examples.html#graphframes.examples.BeliefPropagation









------------------------------------------------------------------------------------------------------------------------------------------------------------

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
