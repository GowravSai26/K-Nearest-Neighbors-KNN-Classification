# Task 6: Interview Questions and Answers

### 1. How does the KNN algorithm work?
The K-Nearest Neighbors (KNN) algorithm is a simple, instance-based learning method that works on the principle of "birds of a feather flock together." To classify a new data point, it does the following:
1.  It calculates the distance from the new point to every single point in the training dataset.
2.  It identifies the 'K' closest points (the "nearest neighbors").
3.  It takes a majority vote among those neighbors. The class that appears most frequently among the neighbors is assigned to the new data point.

---
### 2. How do you choose the right K?
The choice of K is critical and represents a trade-off between bias and variance.

* **A small K** (e.g., K=1) makes the model very sensitive to noise and outliers, leading to **overfitting**.
* **A large K** makes the model more robust to noise but can **oversmooth** the decision boundary, leading to **underfitting**.

The best way to choose K is to experiment. A common method is to plot the model's accuracy on a test set for a range of K values (e.g., 1 to 25). The value of K that gives the highest accuracy is usually the best choice. It's also a good practice to use an odd number for K to avoid ties.

---
### 3. Why is normalization important in KNN?
Normalization (or standardization) is **extremely important** for KNN. KNN is a distance-based algorithm, meaning it relies on calculating the distance between data points. If features are on different scales (e.g., age from 20-70 and salary from 50,000-200,000), the feature with the larger scale will dominate the distance calculation, making the model incorrectly believe that feature is more important. Normalization brings all features to the same scale, ensuring each one contributes equally to the distance measurement.

---
### 4. What is the time complexity of KNN?
KNN is known as a "lazy learner" because it has no traditional training phase.

* **Training Time Complexity:** **O(1)**, because all it does is store the entire training dataset in memory.
* **Prediction Time Complexity:** **O(N * D)**, where N is the number of samples in the training set and D is the number of features. This is because, for every new point, it must calculate the distance to all N training points. This makes prediction very slow for large datasets.

---
### 5. What are pros and cons of KNN?
* **Pros:**
    * **Simple and Intuitive:** Very easy to understand and implement.
    * **No Training Phase:** It's a lazy learner, so it can be updated with new data easily.
    * **Non-linear:** Can learn complex, non-linear decision boundaries.

* **Cons:**
    * **Slow Prediction:** Can be very slow and computationally expensive for large datasets.
    * **Curse of Dimensionality:** Performance degrades as the number of features increases.
    * **Sensitive to Scale:** Requires feature normalization to perform well.
    * **Needs a lot of Memory:** Must store the entire training dataset.

---
### 6. Is KNN sensitive to noise?
**Yes**, especially with a small value of K. If K=1, a single noisy data point or an outlier can easily cause a misclassification for any new point that happens to be near it. Using a **larger K** makes the model more robust to noise because the final prediction is based on a majority vote of more neighbors, effectively smoothing out the influence of individual noisy points.

---
### 7. How does KNN handle multi-class problems?
KNN handles multi-class problems **naturally and easily**. The algorithm's logic doesn't change. When it finds the K nearest neighbors for a new data point, it simply takes a majority vote among all the classes present in those neighbors. The class with the most "votes" is assigned to the new point.

---
### 8. What's the role of distance metrics in KNN?
The distance metric is the **core of the algorithm** because it defines how "nearness" is calculated.
* **Euclidean Distance:** The most common metric, representing the straight-line distance between two points. It's the default in most libraries.
* **Manhattan Distance:** Another popular choice, which measures distance by summing the absolute differences of the coordinates (like navigating city blocks).

The choice of distance metric depends on the nature of the data and can significantly affect the model's performance.