These scripts process sociological data, such as persons' description features such as Country, Specialization, Academic degree, Job, and Stable Income, and find the main clusters.

The script TSNE_clustering.ipynb gets the data from file data.cvs then create the pairwise distance matrix for clustering. The distance between two descriptions is the number of feature mismatches. So we can group the people with similar features into one cluster. To make the clustering, we use the t-SNE algorithm with the number of clusters defined by the KMeans method. The clustering procedure gathers samples (persons) in groups according to their descriptions (features).

To build sociological portraits, we use raw data from the file raw_data_3.csv. The script sociological_portraits.ipynb finds the most frequent combinations of features in the data set and prints them along with their frequency.

The script Clustering_by_country.ipynb takes the data about people's locations from file data_countries_2.csv. In this document formed from the sample data, 1 means the cell of the person's location country, and 0's are stated in the others cells. 

The script computes a pairwise distance matrix (by country) and makes clusters. We set 0 in the new data frame cell if two raws with persons' features are equal. Otherwise, we put 1.

We imply the t-SNE algorithm for the new data frame and visualize the clusters. 
