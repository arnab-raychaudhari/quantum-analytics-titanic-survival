# quantum-analytics-titanic-survival
This project explores how Quantum Machine Learning (QML) techniques compare against traditional machine learning approaches for a binary classification problem: predicting passenger survival on the Titanic.

The project was completed to investigate multiple modeling approaches:

* Classical Machine Learning
* Random Forest Classification
* Gaussian Naive Bayes
* Quantum Circuit-Based Classification
* Variational Quantum Classifier (VQC)
* Quantum-Enhanced Naive Bayes

The objective was to evaluate whether quantum feature encoding and variational quantum circuits can provide meaningful predictive performance compared with classical methods.

## Research Question

Can quantum machine learning techniques achieve competitive classification performance on a real-world analytics dataset when compared to established classical machine learning algorithms?

##  Dataset

The project uses the well-known Titanic Survival Dataset, containing passenger information such as:

* Passenger Class (Pclass)
* Sex
* Age
* Fare
* Number of Siblings/Spouses
* Number of Parents/Children
* Embarkation Port

Target Variable:

* Survived
    * 0 = Did Not Survive
    * 1 = Survived

## Methodology

### Phase I – Classical Machine Learning

#### Data Preprocessing

The dataset was cleaned and transformed through:

* Missing value treatment
* Removal of high-nullity columns (Cabin)
* Median imputation for Age
* Mode imputation for Embarked
* Removal of high-cardinality identifiers
    * PassengerId
    * Name
* Label Encoding of categorical features
* Min-Max normalization of numerical variables

These steps ensured that the data was suitable for machine learning workflows.

#### Classical Models

Implemented models included:

1. Random Baseline Classifier
2. Random Forest Classifier
3. Gaussian Naive Bayes

Evaluation metrics:

* Accuracy
* Precision
* Recall
* Specificity
* Negative Predictive Value (NPV)
* Confusion Matrix

### Phase II – Quantum Machine Learning

Two quantum classification approaches were explored.

#### Approach 1: Custom Quantum Circuits

Classical features were encoded into quantum gate parameters:

* θ (theta)
* φ (phi)
* λ (lambda)
* ω (omega)

Features used:

* Sex
* Passenger Class
* Age
* Embarkation Port

Quantum circuits were built using:

* Hadamard Gates
* U Gates
* Measurement-Based Classification

A second version introduced:

* Quantum Entanglement
* CNOT Gates

to capture more complex feature relationships.

#### Approach 2: Variational Quantum Classifier (VQC)

The Variational Quantum Classifier was implemented using:

* Qiskit
* ZZFeatureMap
* RealAmplitudes Ansatz
* SPSA Optimizer

### Quantum Machine Learning Pipeline

```mermaid
flowchart LR

A[Titanic Dataset]
--> B[Data Cleaning & Feature Engineering]

B --> C[Feature Selection]
C --> D[Quantum Encoding<br>ZZFeatureMap]

D --> E[Variational Circuit<br>RealAmplitudes]

E --> F[Quantum Simulator<br>Qiskit Aer]

F --> G[SPSA Optimizer]

G --> H[Binary Classification<br>Survived / Not Survived]
```
This architecture enables trainable quantum circuits to learn decision boundaries from classical data.

### Phase III – Quantum Naive Bayes

A hybrid quantum-classical workflow was developed:

1. Encode features into a quantum circuit
2. Generate measurement probabilities
3. Use quantum outputs as inputs to a Gaussian Naive Bayes classifier

This approach demonstrates how quantum-generated features can augment classical machine learning pipelines.

## Technologies Used

### Programming

* Python

Libraries

* Pandas
* NumPy
* Scikit-Learn
* Matplotlib
* Qiskit
* Qiskit Aer
* Qiskit Machine Learning
* Qiskit Algorithms

### Quantum Components

* Quantum Circuits
* Hadamard Gates
* U Gates
* CNOT Gates
* ZZFeatureMap
* RealAmplitudes Ansatz
* SPSA Optimizer
* Variational Quantum Classifier (VQC)

## Results

| Model | Accuracy | Notes |
|---------|---------:|---------|
| Random Baseline Classifier | 50.14% | Random guessing benchmark |
| Quantum Hadamard Classifier | 27.50% | Basic quantum feature encoding using Hadamard gates |
| Quantum Entangled Classifier | 53.54% | Improved performance through qubit entanglement |
| Variational Quantum Classifier (VQC) | 74.30% | Trainable quantum circuit using ZZFeatureMap and RealAmplitudes |
| Gaussian Naive Bayes (Classical) | 78.79% | Best-performing classical probabilistic model |
| Quantum-Enhanced Naive Bayes | 78.79% | Hybrid quantum-classical workflow with comparable performance |

| Approach | Method | Accuracy |
|-----------|----------|----------:|
| Classical ML | Random Baseline | 50.14% |
| Classical ML | Gaussian Naive Bayes | 78.79% |
| Quantum ML | Hadamard Circuit Classifier | 27.50% |
| Quantum ML | Entangled Circuit Classifier | 53.54% |
| Quantum ML | Variational Quantum Classifier (VQC) | 74.30% |
| Hybrid Quantum-Classical | Quantum Naive Bayes | 78.79% |

## Method Comparison

| Method | Quantum Encoding | Entanglement | Trainable Parameters |
|----------|----------------|-------------|---------------------|
| Hadamard Classifier | ✓ | ✗ | ✗ |
| Entangled Classifier | ✓ | ✓ | ✗ |
| VQC | ✓ | ✓ | ✓ |
| Quantum Naive Bayes | ✓ | ✓ | Limited |

### Key Observations

- Classical Gaussian Naive Bayes achieved the highest overall accuracy (**78.79%**).
- The Variational Quantum Classifier (VQC) demonstrated competitive performance (**74.30%**) despite being executed on a quantum simulator.
- Entanglement improved the performance of custom quantum circuits from **27.50%** to **53.54%**.
- Hybrid quantum-classical approaches achieved results comparable to classical machine learning methods.
- Results suggest that variational quantum algorithms are promising for future analytics applications, although classical methods remain superior for this dataset.

## Future Improvements

* Execute experiments on real quantum hardware
* Explore Quantum Kernel Methods
* Investigate Quantum Neural Networks (QNNs)
* Improve feature engineering
* Perform hyperparameter optimization for VQC architectures
* Benchmark against Gradient Boosting and XGBoost models
