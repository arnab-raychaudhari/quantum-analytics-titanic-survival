# Titanic Survival - Hybrid Quantum-Classical Analytics Framework for Predictive Modeling
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

The project uses the well-known [Titanic Survival Dataset](https://github.com/arnab-raychaudhari/quantum-analytics-titanic-survival/blob/db7b047c6ec44e4fd8dab1ce77e3caa435fd0d7f/titanic_train.csv), containing passenger information such as:

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

* [Python](https://github.com/arnab-raychaudhari/quantum-analytics-titanic-survival/blob/d321f74fc43e770b0c1bd7f047c68f68f6d2de85/qa-titanic-survival.ipynb)

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
| Random Baseline Classifier | 48.74% | Random guessing benchmark |
| Quantum Hadamard Classifier | 27.93% | Basic quantum feature encoding using Hadamard gates |
| Quantum Entangled Classifier | 55.31% | Improved performance through qubit entanglement |
| Variational Quantum Classifier (VQC) | 66.48% | Trainable quantum circuit using ZZFeatureMap and RealAmplitudes |
| Gaussian Naive Bayes (Classical) | 77.09% | Best-performing classical probabilistic model |
| Quantum-Enhanced Naive Bayes | 78.79% | Hybrid quantum-classical workflow with comparable performance |

| Approach | Method | Accuracy |
|-----------|----------|----------:|
| Classical ML | Random Baseline | 48.74% |
| Classical ML | Gaussian Naive Bayes | 77.09% |
| Quantum ML | Hadamard Circuit Classifier | 27.93% |
| Quantum ML | Entangled Circuit Classifier | 55.31% |
| Quantum ML | Variational Quantum Classifier (VQC) | 66.48% |
| Hybrid Quantum-Classical | Quantum Naive Bayes | 78.79% |

<h3>Random Classifier - Confusion Matrix</h3>

<img src="https://github.com/arnab-raychaudhari/quantum-analytics-titanic-survival/blob/87cbe19243c4852b924806d10d6c3ac2e14699cd/Random%20Classifier%20-%20Confusion%20Matrix.png" width="800" />

<h3>NB - Confusion Matrix</h3>

<img src="https://github.com/arnab-raychaudhari/quantum-analytics-titanic-survival/blob/87cbe19243c4852b924806d10d6c3ac2e14699cd/NB%20-%20Confusion%20Matrix.png" width="800" />

<h3>Hadamard Quantum Circuit</h3>

<img src="https://github.com/arnab-raychaudhari/quantum-analytics-titanic-survival/blob/87cbe19243c4852b924806d10d6c3ac2e14699cd/Hadamard%20Quantum%20Circuit.png" width="800" />

<h3>Entangled Quantum Circuit</h3>

<img src="https://github.com/arnab-raychaudhari/quantum-analytics-titanic-survival/blob/87cbe19243c4852b924806d10d6c3ac2e14699cd/Entangled%20Quantum%20Circuit.png" width="800" />

<h3>ZZ-Feature-Map</h3>

<img src="https://github.com/arnab-raychaudhari/quantum-analytics-titanic-survival/blob/f1e107743e97b223384705bd6db9fef96a9b53a5/ZZ-Feature-Map.png" width="800" />

<h3>Real Amplitude Circuit</h3>

<img src="https://github.com/arnab-raychaudhari/quantum-analytics-titanic-survival/blob/f1e107743e97b223384705bd6db9fef96a9b53a5/Real%20Amplitude%20Circuit.png" width="800" />

<h3>Variational Circuit</h3>

<img src="https://github.com/arnab-raychaudhari/quantum-analytics-titanic-survival/blob/f979290786eb7b0d6510e9be383f3718d1b9e383/Variational%20Circuit.png" width="800" />

## Method Comparison

| Method | Quantum Encoding | Entanglement | Trainable Parameters |
|----------|----------------|-------------|---------------------|
| Hadamard Classifier | ✓ | ✗ | ✗ |
| Entangled Classifier | ✓ | ✓ | ✗ |
| VQC | ✓ | ✓ | ✓ |
| Quantum Naive Bayes | ✓ | ✓ | Limited |

### Key Observations

- **Quantum-Enhanced Naive Bayes** achieved the highest overall accuracy (**78.79%**).
- The Variational Quantum Classifier (VQC) demonstrated competitive performance (**66.48%**) despite being executed on a quantum simulator.
- **Entanglement** improved the performance of custom quantum circuits from **27.93%** to **55.31%**.
- Hybrid quantum-classical approaches achieved results comparable to classical machine learning methods.
- Results suggest that **variational quantum algorithms are promising for future analytics applications**, although classical methods remain superior for this dataset.

## Future Improvements

* Execute experiments on real quantum hardware
* Explore Quantum Kernel Methods
* Investigate Quantum Neural Networks (QNNs)
* Improve feature engineering
* Perform hyperparameter optimization for VQC architectures
* Benchmark against Gradient Boosting and XGBoost models
