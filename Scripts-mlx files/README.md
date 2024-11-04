
# Analysis of Neural Network Model Performance for Intrusion Detection

This project explores various neural network models for intrusion detection, assessing each model's architecture, training methodology, and performance metrics. The aim is to identify the optimal model configuration balancing accuracy, precision, recall, F1 score, and time efficiency.

## Table of Contents
1. [Architectural Overview](#architectural-overview)
2. [Performance Matrix - Testing](#performance-matrix---testing)
3. [Observations](#observations)
4. [Conclusion](#conclusion)
5. [Performance Metrics Explanation](#performance-metrics-explanation)

## Architectural Overview

This analysis includes multiple neural network models with distinct architectures. Each model varies in hidden layers, neuron count, initialization, training function, and performance function. Here’s a breakdown of each model's configuration:

| Model | Hidden Layers | Neurons per Layer | Initialization | Training Function | Performance Function | Learning Rate | Momentum | Epochs | Data Division | Activation |
|-------|---------------|-------------------|----------------|-------------------|----------------------|---------------|----------|--------|---------------|------------|
| Model 1 (Cross-Validation, Best Observed) | 3 | 36 | `feedforwardnet(36,1,3)` | `trainlm` (Levenberg-Marquardt) | MSE | 0.089976 | 0.88551 | 22 | `dividetrain` (all data) | `tansig` (Tan-sigmoid) |
| Model 2 (Cross-Validation, Best Feasible) | 1 | 29 | `feedforwardnet(repmat(29,1,1))` | `traincgp` (Conjugate Gradient Powell) | MSE | 0.051679 | 0.68386 | 25 | `dividetrain` (all data) | `purelin` (Pure Linear) |
| Model 3 (No Cross-Validation, Best Observed) | 3 | 49 | `feedforwardnet(repmat(49,1,3))` | `traincgb` (Conjugate Gradient Backprop) | MSE | 0.019044 | 0.68859 | 41 | `dividetrain` (all data) | `tansig` (Tan-sigmoid) |
| Model 4 (No Cross-Validation, Best Feasible) | 3 | 40 | `feedforwardnet(repmat(40,1,3))` | `trainrp` (Resilient Backpropagation) | MSE | 0.032172 | 0.77721 | 35 | `dividetrain` (all data) | `tansig` (Tan-sigmoid) |

Each model is tailored to optimize different performance aspects based on network configuration and training functions. The architecture's complexity and parameter settings are carefully selected to enhance model robustness, convergence, and accuracy.

## Performance Matrix - Testing

The testing phase evaluates each model on various performance metrics. These metrics provide insight into the model's accuracy, precision, recall, and F1 score across different testing scenarios. Here is a summary:

| Model | Dataset Coverage | Accuracy | Precision | Recall | F1 Score |
|-------|-------------------|----------|-----------|--------|----------|
| Model 1 (Cross-Validation, Best Observed) | 20% of 10% of the dataset | 99.9% | 99.95% | 99.93% | 99.94% |
| Model 1 (Cross-Validation, Best Observed) | Full dataset | 99.9% | 99.96% | 99.91% | 99.94% |
| Model 2 (Cross-Validation, Best Feasible) | 20% of 10% of the dataset | 98.98% | 99.88% | 98.86% | 99.36% |
| Model 2 (Cross-Validation, Best Feasible) | Full dataset | 99.72% | 99.86% | 99.79% | 99.83% |
| Model 3 (No Cross-Validation, Best Observed) | 20% of 10% of the dataset | 99.23% | 99.92% | 99.13% | 99.52% |
| Model 4 (No Cross-Validation, Best Feasible) | 20% of 10% of the dataset | 99.26% | 99.78% | 99.30% | 99.54% |
| Model 4 (No Cross-Validation, Best Feasible) | Full dataset | 99.76% | 99.80% | 99.89% | 99.85% |

### Key Findings:
- **Model 1** demonstrated the highest accuracy and reliability, particularly with cross-validation.
- **Model 2** offered a balance of time efficiency and reliability, with slightly lower but still impressive performance metrics.
- **Models 3 and 4** (without cross-validation) maintained high metrics but showed some variability across subsets.

## Observations

- **Time Consumption**: Model 2 emerged as the most time-efficient model, suitable for scenarios requiring quick results with reliable performance.
- **Overall Performance**: Model 1 excelled in all performance metrics, making it the best choice for accuracy and robustness.
- **Reliability**: Models 1 and 2 are both reliable; Model 1 is optimal for high-performance applications, while Model 2 is preferable when time efficiency is essential.

## Conclusion

The analysis highlights the importance of selecting the right model configuration based on project requirements. 

- **Model 1**: Best overall model due to high accuracy, precision, recall, and F1 score, especially in cross-validation settings.
- **Model 2**: Best model for time-sensitive applications due to its efficient performance with relatively high metrics.

This study demonstrates that the optimal neural network model for intrusion detection is not necessarily the most complex but rather the one that aligns best with the intended application's requirements.

## Performance Metrics Explanation

The following metrics were used to evaluate each model's performance:

- **Accuracy**: Measures the proportion of correct predictions over the total predictions. It is useful for overall assessment but may be misleading with class imbalance.
  
  \[
  \text{Accuracy} = \frac{\text{True Positives + True Negatives}}{\text{Total Observations}}
  \]

- **Precision**: Focuses on the correctness of positive predictions by assessing the proportion of true positive predictions out of all positive predictions made.

  \[
  \text{Precision} = \frac{\text{True Positives}}{\text{True Positives + False Positives}}
  \]

- **Recall**: Measures the ability to capture all actual positive cases, assessing the proportion of true positive predictions out of all actual positives.

  \[
  \text{Recall} = \frac{\text{True Positives}}{\text{True Positives + False Negatives}}
  \]

- **F1 Score**: Combines precision and recall into a single metric, providing a balanced measure especially useful in the presence of class imbalance.

  \[
  \text{F1 Score} = 2 \times \frac{\text{Precision} \times \text{Recall}}{\text{Precision + Recall}}
  \]
