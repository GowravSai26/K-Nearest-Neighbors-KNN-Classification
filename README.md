# K-Nearest Neighbors (KNN) for Iris Classification

### Project Objective
The objective of this project is to implement and understand the K-Nearest Neighbors (KNN) algorithm for a classification problem. The model is trained on the classic Iris dataset to classify flowers into one of three species.

---
### Workflow

The project follows a structured approach from data preparation to model tuning, evaluation, and visualization.

#### 1. Data Preparation
* **Dataset Loading:** The Iris dataset was loaded from Scikit-learn. For the purpose of clear visualization, only two features (Sepal Length and Sepal Width) were used.
* **Feature Normalization:** The features were normalized using `StandardScaler`. This is a critical step for KNN, as it is a distance-based algorithm and requires all features to be on the same scale.

#### 2. Finding the Optimal K
The performance of a KNN model is highly dependent on the choice of 'K' (the number of neighbors).
* **Experimentation:** A loop was run to train and evaluate the KNN model for K values ranging from 1 to 25.
* **Visualization:** The accuracy for each K was plotted on a graph, allowing for the visual selection of the optimal K value that yielded the highest accuracy.

#### 3. Model Training and Evaluation
Using the optimal K value found in the previous step, a final `KNeighborsClassifier` model was trained. The model's performance was then evaluated on the test set using:
* **Accuracy Score:** To get a general measure of correctness.
* **Confusion Matrix:** To get a detailed breakdown of correct and incorrect predictions for each of the three Iris species.

#### 4. Visualizing Decision Boundaries
A key part of this task was to create a visualization of the model's decision boundaries. This plot shows the regions in the feature space that the model has learned to associate with each class. The final plot clearly illustrates how the KNN algorithm separates the different Iris species based on their sepal measurements.

---
### Tools and Libraries Used
* **Python**
* **Pandas**
* **Scikit-learn**
* **Matplotlib**
* **Seaborn**

---
### How to Run

1.  Clone the repository to your local machine.
2.  Create and activate a Python virtual environment.
3.  Install the required dependencies from the `requirements.txt` file:
    ```bash
    pip install -r requirements.txt
    ```
4.  Open and run the Jupyter Notebook (`.ipynb` file) in a compatible editor like VS Code.
