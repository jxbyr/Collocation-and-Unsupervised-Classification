<a id="readme-top"></a>

Open in Colab: [Unit 1](https://drive.google.com/file/d/1LLOBi53D6LdkLUI9n428U8uE8t-YNHuU/view?usp=share_link)
 [Unit 2](https://drive.google.com/file/d/1YMPrUypxgMbJj2PfC4ZrShADtX7jP_bc/view?usp=share_link)

<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a">
    <img src="logo.png" alt="Logo">
  </a>

  <h3 align="center">GEOL0069 Week 4 Practical: Collocation and Unsupervised Classification</h3>

  <p align="center">
    Sea Ice and Lead Classification.
  </p>
</div>



<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#introduction-to-unsupervised-learning-methods-bishop2006pattern">Introduction to Unsupervised Learning Methods</a>
      <ul>
        <li><a href="#introduction-to-k-means-clustering">Introduction to K-means Clustering</a></li>
        <li><a href="#gaussian-mixture-models-gmm-bishop2006pattern">Introduction to Gaussian Mixture Models</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->

# Introduction to Unsupervised Learning Methods `bishop2006pattern`

## Introduction to K-means Clustering

K-means clustering is a type of unsupervised learning algorithm used for partitioning a dataset into a set of k groups (or clusters), where k represents the number of groups pre-specified by the analyst. It classifies the data points based on the similarity of the features of the data {cite}`macqueen1967some`. The basic idea is to define k centroids, one for each cluster, and then assign each data point to the nearest centroid, while keeping the centroids as small as possible.

### Why K-means for Clustering?

K-means clustering is particularly well-suited for applications where:

- **The structure of the data is not known beforehand**: K-means doesn’t require any prior knowledge about the data distribution or structure, making it ideal for exploratory data analysis.
- **Simplicity and scalability**: The algorithm is straightforward to implement and can scale to large datasets relatively easily.

### Key Components of K-means

1. **Choosing K**: The number of clusters (k) is a parameter that needs to be specified before applying the algorithm.
2. **Centroids Initialization**: The initial placement of the centroids can affect the final results.
3. **Assignment Step**: Each data point is assigned to its nearest centroid, based on the squared Euclidean distance.
4. **Update Step**: The centroids are recomputed as the center of all the data points assigned to the respective cluster.

### The Iterative Process of K-means

The assignment and update steps are repeated iteratively until the centroids no longer move significantly, meaning the within-cluster variation is minimised. This iterative process ensures that the algorithm converges to a result, which might be a local optimum.

### Advantages of K-means

- **Efficiency**: K-means is computationally efficient.
- **Ease of interpretation**: The results of k-means clustering are easy to understand and interpret.



## Introduction to Gaussian Mixture Models (GMM)

Gaussian Mixture Models (GMM) are a probabilistic model for representing normally distributed subpopulations within an overall population. The model assumes that the data is generated from a mixture of several Gaussian distributions, each with its own mean and variance {cite}`reynolds2009gaussian, mclachlan2004finite`. GMMs are widely used for clustering and density estimation, as they provide a method for representing complex distributions through the combination of simpler ones.

### Why Gaussian Mixture Models for Clustering?

Gaussian Mixture Models are particularly powerful in scenarios where:

- **Soft clustering is needed**: Unlike K-means, GMM provides the probability of each data point belonging to each cluster, offering a soft classification and understanding of the uncertainties in our data.
- **Flexibility in cluster covariance**: GMM allows for clusters to have different sizes and different shapes, making it more flexible to capture the true variance in the data.

### Key Components of GMM

1. **Number of Components (Gaussians)**: Similar to K in K-means, the number of Gaussians (components) is a parameter that needs to be set.
2. **Expectation-Maximization (EM) Algorithm**: GMMs use the EM algorithm for fitting, iteratively improving the likelihood of the data given the model.
3. **Covariance Type**: The shape, size, and orientation of the clusters are determined by the covariance type of the Gaussians (e.g., spherical, diagonal, tied, or full covariance).

### The EM Algorithm in GMM

The Expectation-Maximization (EM) algorithm is a two-step process:

- **Expectation Step (E-step)**: Calculate the probability that each data point belongs to each cluster.
- **Maximization Step (M-step)**: Update the parameters of the Gaussians (mean, covariance, and mixing coefficient) to maximize the likelihood of the data given these assignments.

This process is repeated until convergence, meaning the parameters do not significantly change from one iteration to the next.

### Advantages of GMM

- **Soft Clustering**: Provides a probabilistic framework for soft clustering, giving more information about the uncertainties in the data assignments.
- **Cluster Shape Flexibility**: Can adapt to ellipsoidal cluster shapes, thanks to the flexible covariance structure.



<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- GETTING STARTED -->
## Getting Started

We aim to classify the echoes in leads and sea ice, produce an average echo shape and the standard deviation for these two classes.  Then, we can quantify echo classification against the ESA official classification using a confusion matrix.

We colocate images from pairs of satellites: illustrated, for example, by collocating Sentinel-3 (300m resolution) and Sentinel-2 imagery (10m resolution) as well as altimetry data from Sentinel-3.  This set of data is then used to deploy unsupervised classification algorithms.

Programing is coded with Python on the google colaboratory platform.

### Prerequisites

Mount your Google Drive on Colab using:

  ```sh
    from google.colab import drive
    drive.mount('/content/drive')
  ```

### Installation

You will need to install the following packages to successfully run this project:

*pip installations

  ```sh
  !pip install rasterio
  
  !pip install netCDF4
  
  !pip install basemap
  
  !pip install cartopy
  ```
As well as download the Sentinal-2 Optical Data:

[]()

and Sentinal-3 OLCI Data:

[]()

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- CONTACT -->
## Contact

James Byrne - zcfbjby@ucl.ac.uk

Project Link: [https://github.com/jxbyr/Collocation-and-Unsupervised-Classification](https://github.com/jxbyr/Collocation-and-Unsupervised-Classification)

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- ACKNOWLEDGMENTS -->
## Acknowledgments

[Read Me Template](https://github.com/othneildrew/Best-README-Template/blob/main/README.md?plain=1)

[GEOL0069_25-26 Moodle](https://moodle.ucl.ac.uk/course/view.php?id=51136)

[Dr Tsamados](m.tsamados@ucl.ac.uk)

Project serves as my submission for the GEOL0069 week 4 pratical assignment.

<p align="right">(<a href="#readme-top">back to top</a>)</p>
