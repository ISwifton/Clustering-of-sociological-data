# Clustering of sociological data
The script gets sociological data from file .cvs. The data include persons' description features such as Country, Specialization, Academic degree, Job, and Stable Income.
Then we create the pairwise distance matrix to minimize the number of clusters. The distance between two descriptions is the number of feature mismatches. So we can group the people with similar features into one cluster.
To make the clustering, we use the t-SNE algorithm with the number of clusters defined by KMeans method. The clustering procedure gathers samples (persons) in groups according to their descriptions (features).
