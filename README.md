# GA-Based Feature Selection for Medical Diagnosis

## Project Overview

This project implements a **Genetic Algorithm (GA)-based feature selection approach** for breast cancer diagnosis using the Breast Cancer Wisconsin Diagnostic (WDBC) dataset.

The primary objective is to identify the most relevant features from the original dataset while maintaining high classification performance. A Logistic Regression classifier is used to evaluate the selected features.

By combining evolutionary optimization with machine learning, the proposed approach aims to reduce dimensionality, improve model efficiency, and maintain reliable classification performance.

## Objectives

- Implement a Genetic Algorithm for feature selection.
- Identify the most informative features for breast cancer classification.
- Reduce the number of input features from 30 to 10.
- Evaluate classification performance using Logistic Regression.
- Analyze the effectiveness of feature selection through performance metrics and visualizations.

## Dataset

**Dataset:** Breast Cancer Wisconsin Diagnostic (WDBC)

- Total samples: 569
- Original features: 30
- Classes: Malignant and Benign
- Training samples: 455
- Testing samples: 114
- Train-test split: 80:20

The dataset is obtained using Scikit-learn's built-in `load_breast_cancer()` dataset.

## Methodology

The project follows these steps:

1. **Data Loading:** Load the Breast Cancer Wisconsin Diagnostic dataset.
2. **Preprocessing:** Split the dataset into training and testing sets.
3. **Chromosome Encoding:** Represent each candidate feature subset as a binary chromosome, where 1 indicates a selected feature and 0 indicates an excluded feature.
4. **Fitness Evaluation:** Evaluate each chromosome using Logistic Regression and balanced accuracy.
5. **Selection:** Select better-performing chromosomes for reproduction.
6. **Crossover:** Combine parent chromosomes to generate new feature subsets.
7. **Mutation:** Introduce random changes to maintain population diversity.
8. **Elitism:** Preserve the best-performing solutions across generations.
9. **Final Evaluation:** Train and evaluate Logistic Regression using the selected features.

### Fitness Function

The fitness function balances classification performance and feature reduction:

\[
Fitness = BA - \lambda \left(\frac{k}{N}\right)
\]

Where:

- \(BA\) = Balanced Accuracy
- \(\lambda\) = Feature penalty coefficient (0.01)
- \(k\) = Number of selected features
- \(N\) = Total number of original features (30)

The objective is to maximize fitness while selecting a smaller subset of relevant features.

## Experimental Results

The Genetic Algorithm selected **10 features out of the original 30 features**, achieving a 66.67% reduction in dimensionality.

| Evaluation Metric | GA + Logistic Regression |
|---|---:|
| Accuracy | 96.49% |
| Balanced Accuracy | 96.73% |
| Precision | 98.57% |
| Recall | 95.83% |
| F1-score | 97.18% |
| ROC-AUC | 99.60% |
| Original Features | 30 |
| Selected Features | 10 |
| Feature Reduction | 66.67% |

## Selected Features

The Genetic Algorithm identified the following 10 features:

1. Mean radius
2. Mean perimeter
3. Mean concavity
4. Area error
5. Compactness error
6. Worst texture
7. Worst area
8. Worst smoothness
9. Worst concave points
10. Worst symmetry

## Visualizations

The repository includes the following experimental visualizations:

- `ga_convergence.png` – Fitness improvement across Genetic Algorithm generations.
- `selected_features.png` – Visualization of the selected features.
- `confusion_matrix.png` – Classification performance across the two classes.
- `roc_curve.png` – ROC curve and AUC performance.

## Technologies Used

- Python
- NumPy
- Pandas
- Scikit-learn
- Matplotlib
- Genetic Algorithm
- Logistic Regression
- Google Colab
- Git and GitHub

## Project Structure

```text
GA-Based-Feature-Selection-Medical-Diagnosis/
│
├── ga_feature_selection.py
├── selected_features.csv
├── performance_results.csv
│
├── ga_convergence.png
├── selected_features.png
├── confusion_matrix.png
├── roc_curve.png
│
├── README.md
└── requirements.txt
```

## Installation and Execution

### 1. Clone the repository

```bash
git clone https://github.com/PallaviChikkala/GA-Based-Feature-Selection-Medical-Diagnosis.git
```

### 2. Navigate to the project directory

```bash
cd GA-Based-Feature-Selection-Medical-Diagnosis
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the project

```bash
python ga_feature_selection.py
```

## Conclusion

The experimental results demonstrate that Genetic Algorithm-based feature selection can substantially reduce the number of input features while maintaining strong classification performance.

The proposed approach reduced the feature set from 30 to 10 while achieving 96.49% accuracy and 99.60% ROC-AUC using Logistic Regression.

This project demonstrates the application of evolutionary optimization techniques in machine learning-based medical diagnosis.

## Disclaimer

This project is developed for academic and research purposes only. It is not intended to replace professional medical diagnosis or clinical decision-making.

## Author

**Pallavi Chikkala**  
**T Hasini**  
B.Tech – Artificial Intelligence  
SRM Institute of Science and Technology
