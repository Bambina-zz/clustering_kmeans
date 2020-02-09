# Determining The Optimal Number Of Clusters


## Elbow method

The main idea of the Elbow method is to minimize the total variance of clusters.

1. Compute clustering algorithm (e.g., k-means clustering) for different values of k.
1. For each k, calculate the total within-cluster sum of square(wss).
1. Plot the curve of wss according to the number of clusters k.
1. The location of a bend (knee) in the plot is generally considered as an indicator of the appropriate number of clusters.


## Silhouette method

The main idea is to compare the Silhouette Coefficient over all samples.

1. Compute clustering algorithm (e.g., k-means clustering) for different values of k.
1. For each k, get the mean distance between (i) and all other data points in the same cluster. Define this as (a).
1. Get the mean distance between (i) and all data points in any other cluster. Define the smallest distance as (b).
1. The Silhouette Coefficient for (i) is (b - a) / max(a, b). Get the mean Silhouette Coefficient over all samples.
1. Plot all samples' Silhouette Coefficient for different values of k.
1. Select the one in which relatively most samples hit the higher Silhouette Coefficient.


## Gap statistic method

The main idea of this method is to compare the gap between the total sum of squares of variation of original clusters and modified clusters which incorporate new expected values.

1. Cluster the observed data, varying the number of clusters from k = 1, …, kmax, and compute the corresponding total sum of squares of variation (Wk).
1. Generate B reference data sets over the range of the observed values. Cluster each of these reference with varying number of clusters k = 1, …, kmax, and compute the corresponding total sum of squares of variation (Wkb).
1. Compute the estimated gap statistic: Gap(k)=(1/B)∑log(Wkb)−log(Wk)
1. Choose the number of clusters as the smallest value such that Gap(k) >= Gap(k+1) - S(k+1).
