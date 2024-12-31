# K-Means-Point-Cloud-Clustering

Overview

This project implements a K-Means clustering algorithm for 3D point cloud data using Python. It leverages the Open3D library for point cloud handling, scikit-learn for clustering, and Matplotlib for visualization. The main goal is to segment the point cloud into distinct clusters, which can be useful for various applications like object detection, scene segmentation, and robotics.

Approach

1. Point Cloud Loading

The Open3D library is used to read point cloud data from various formats (e.g., .ply, .pcd).

All points from the loaded point cloud are extracted into a NumPy array for further processing.

2. Downsampling

To ensure efficient processing, point clouds with more than a specified number of points (max_points) are downsampled by random selection. This step reduces computational overhead while preserving spatial distribution.

3. K-Means Clustering

The K-Means algorithm from scikit-learn is applied to segment the point cloud into n_clusters.

Cluster labels are assigned to each point based on proximity to cluster centroids.

4. Visualization

The results are visualized using Matplotlib's 3D plotting capabilities.

Points are color-coded by their cluster labels, with predefined colors cycling for visualization.

Design Decisions

Downsampling:

Chosen to optimize performance for large point clouds without significantly affecting clustering accuracy.

Predefined Colors:

A fixed color palette ensures visual clarity, with fallback for cases where the number of clusters exceeds the color set.

Error Handling:

Exception handling ensures robustness when processing multiple files, skipping problematic files and logging errors.

Modular Design:

The implementation separates point cloud processing, clustering, and visualization for reusability and extensibility.

Instructions for Running the Code

Install Dependencies:
Ensure the following Python libraries are installed:

pip install numpy open3d scikit-learn matplotlib

Prepare Point Cloud Files:

Place your point cloud files in a directory.

Supported formats include .ply, .pcd, etc.

Run the Code:

Modify the file_paths variable in the main function to include the paths to your point cloud files.

Adjust the parameters n_clusters and max_points as needed.

Execute the script:

python kmeans_point_cloud_clustering.py

View Results:

The script will display 3D visualizations of the clustered point clouds.

Relevant Details

Cluster Colors:
The script uses six predefined colors (red, green, blue, yellow, magenta, cyan). Additional clusters reuse these colors cyclically.

Output:
The clustering results include:

Clustered points

Cluster labels

Cluster centroids

Error Messages:
If a file cannot be processed, an error message is displayed, and the script continues with other files.

Example

Input:

Point cloud files: Ideal PCD.ply, Real World PCD.pcd

Parameters: n_clusters=6, max_points=10000

Output:

Visualizations of clustered point clouds with distinct colors.
