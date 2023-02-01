These scripts process sociological data on researchers' relocations such as Country, Specialization, Academic degree, Job, and Stable Income, find the main clusters, and create the average portraits for each cluster. The script TSNE_clustering.ipynb gets the data from file data.cvs and then makes the pairwise distance matrix for clustering. The distance between two descriptions is the number of feature mismatches. So we can group the people with similar features into one cluster. To make the clustering, we use the t-SNE algorithm with the number of clusters defined by the KMeans method. The clustering procedure gathers samples (persons) in groups according to their descriptions (features).

To build sociological portraits, we use raw data from the file raw_data_3.csv. The script sociological_portraits.ipynb finds the most frequent combinations of features in the data set and prints them along with their frequency.

The script Clustering_by_country.ipynb takes the data about people's locations from file data_countries_2.csv. In this document formed from the sample data, 1 means the cell of the person's location country, and 0's are stated in the others cells. The script computes a pairwise distance matrix (by country) and makes clusters. We set 0 in the new data frame cell if two raws with persons' features are equal. Otherwise, we put 1. We use the t-SNE algorithm for the new data frame and visualize the clusters.

The script Clustering_by_job.ipynb takes the data about people's employment from file data_job.csv. There are four fields: HasJob, StableIncome, KeepSpecialization, and FullTime. Then, the script computes the pairwise distance matrix, makes clustering, and visualizes the results.

The script Clustering by all_fields.ipynb takes aggregated data from all_data_200.csv. The file contains five fields describing the countries of relocation, four fields describing the people's employment, four fields stating academic degrees (Bachelor, Master, Ph.D., DSC), and five fields displaying the specializations. Then we build a pairwise distance matrix on the aggregated data and cluster them into 10 clusters. The last step is visualization.

The script Clustering_big_data.ipynb shows how the system works with big data (more than 6000 rows).
The script Clustering_big_data_with_portrets.ipynb, along with the clustering, shows the people's portraits for each cluster. To make them, we build the median matrixes for each cluster and compose the portrait descriptions according to the following designations. 

Column 1 - Country:
Kazakhstan - 2;
Georgia - 4;
Armenia - 5;
Asia - 7;
Europe - 6.

Column 2 - Education (Academic Degrees):
Bachelor's degree - 1;
Master's degree - 2;
Ph.D. - 3;
DSC (Doctor of sciences) - 4.

Column 3 - Employment status:
0 - No job & No Income & No KeepSpecialization & No FullTime;
1 - Has Job & No Income & No KeepSpecialization & No FullTime;
2 - Has Job & Has Income & No KeepSpecialization & No FullTime;
3 - Has Job & Has Income & KeepSpecialization & No FullTime;
4 - Has Job & Has Income & KeepSpecialization & FullTime.

Column 4 - Specialization:
STEM (physicist, mathematician, chemist) - 1,2,3...;
Soft Science - 11, 12, ...19;
20, 21 ... - Others;

Column 5 - Income_confirmation:
No - 1;
Yes - 2.

Cluster 0 (red) - median [[2. 3. 2. 3. 1.]]
Kazakhstan, Ph.D., No Job, STEM, No Income confirmation

Cluster 1 (purple) - median [[ 2.  3.  2. 20.  1.]]

Kazakhstan, Ph.D., No Job, Others, No Income confirmation

Cluster 2 (blue) - median [[ 2.  3.  2. 11.  1.]]

Kazakhstan, Ph.D., No Job, Soft Science, No Income confirmation

Cluster 3 (green) - median [[ 5.  2.  2. 20.  1.]]

Armenia, Master's degree, No Job, Others, No Income confirmation

Cluster 4 (brown) - median [[5. 3. 2. 3. 1.]]

Armenia, Ph.D., No Job, STEM, No Income confirmation

The final script, Clustering_automated_portraits.ipynb creates the portraits for each cluster from medians and automatically builds the labels for the chart.

![Clustering sociological data](https://github.com/ISwifton/Clustering-of-sociological-data/blob/main/clustering.png)

