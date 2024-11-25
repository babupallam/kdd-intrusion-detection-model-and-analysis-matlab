# KDD Intrusion Detection Model and Analysis (MATLAB)

This repository contains a MATLAB-based implementation of an **Intrusion Detection System (IDS)** using **neural networks**, focused on detecting network intrusions with the **KDD Cup '99 dataset**. The project employs advanced machine learning techniques, including **hyperparameter tuning**, **Bayesian optimization**, and **model evaluation**, to create an efficient classification model capable of distinguishing between normal and malicious network activities.

---

## Repository Overview

This repository includes a structured workflow for preprocessing, training, optimizing, and testing a neural network-based IDS. It also explores various experiments to fine-tune the system's performance.

### File Descriptions

1. **idp_01_data_loading.mlx**  
   - Loads the KDD Cup '99 dataset.
   - Prepares the data structure for further processing.
   
2. **idp_02_data_preprocessing.mlx**  
   - Handles data preprocessing tasks, including normalization and feature engineering.
   - Removes redundant features to improve model efficiency.
   
3. **idp_03_bayesian_optimization.mlx**  
   - Conducts Bayesian optimization for hyperparameter tuning.
   - Identifies the best hyperparameter settings for model training.

4. **idp_04_train_final_model.mlx**  
   - Trains the final neural network model using optimized parameters.
   - Visualizes training progress (loss, accuracy).

5. **idp_05_evaluate_model.mlx**  
   - Evaluates the trained model on test data.
   - Generates performance metrics like accuracy, precision, recall, F1-score, and confusion matrix.

6. **idp_06_final_training_and_testing_best_observed.mlx**  
   - Conducts model training and testing using the best hyperparameters identified during Bayesian optimization.

7. **idp_07_final_training_and_testing_best_feasible.mlx**  
   - A streamlined version of the above script focusing on feasible hyperparameters for real-world implementation.

8. **idp_10_exp1_unseen_data_processing_data.mlx**  
   - Processes unseen test data to evaluate generalizability.

9. **idp_11_exp1_unseen_data_testing_best_observed.mlx**  
   - Tests the model on unseen data with the best hyperparameters observed.

10. **idp_12_exp1_unseen_data_testing_best_feasible.mlx**  
    - Similar to the above, but evaluates feasible hyperparameters on unseen data.

11. **idp_15_exp2_multiclass_approach.mlx**  
    - Implements a multiclass classification approach for intrusion detection.

12. **idp_20_exp3_bayesian_optimization_without_cross_validation.mlx**  
    - Explores Bayesian optimization without cross-validation for comparison.

13. **idp_21_exp3_training_and_testing_with_best_feasible.mlx**  
    - Trains and tests the model using the best feasible parameters under Experiment 3.

14. **idp_22_exp3_unseen_data_testing_best_feasible.mlx**  
    - Tests the model on unseen data using the best feasible parameters in Experiment 3.

---

## Key Features

- **Dataset:** Utilizes the KDD Cup '99 dataset, a benchmark dataset for evaluating intrusion detection systems.
- **Optimization:** Includes Bayesian optimization for hyperparameter tuning.
- **Multiclass Classification:** Supports detection of multiple types of network attacks.
- **Experiments:** Contains multiple experimental setups to evaluate the robustness and generalizability of the model.
- **MATLAB Implementation:** Provides `.mlx` files for a clear and interactive workflow.

---

## Installation and Setup

### Prerequisites

- MATLAB R2020b or later.
- Statistics and Machine Learning Toolbox.
- Deep Learning Toolbox.

### Steps to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/babupallam/kdd-intrusion-detection-model-and-analysis-matlab.git
   cd kdd-intrusion-detection-model-and-analysis-matlab
   ```
2. Open MATLAB and navigate to the repository directory.
3. Run the `.mlx` files in sequence for the complete workflow:
   - Start with `idp_01_data_loading.mlx` for loading the dataset.
   - Follow the files in ascending order based on the naming convention.

---

## Results and Analysis

- **Performance Metrics:** The model achieves high accuracy in detecting intrusions and has been evaluated across various experiments.
- **Generalizability:** Evaluated on unseen data to ensure real-world applicability.
- **Multiclass Approach:** Demonstrates capability to classify different attack types effectively.

---

## Contributions

- **Author:** Babu Pallam
- **Mentor:** David Elizondo 

Contributions and feedback are welcome! Please open an issue or submit a pull request for suggestions or improvements.

---

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.
