# KDD Cup '99 Datasets

This directory contains the **KDD Cup '99 Intrusion Detection** datasets, commonly used for evaluating network intrusion detection systems. The KDD Cup dataset provides a comprehensive record of network traffic, which includes various attack patterns and normal traffic, allowing researchers and developers to train, validate, and test machine learning models for intrusion detection.

## Abstract

The KDD Cup '99 dataset is a benchmark dataset in the field of intrusion detection, created for the 1999 Knowledge Discovery and Data Mining (KDD) competition. It contains a diverse set of connection records, each labeled as "normal" or an attack type. With features derived from network traffic statistics, the dataset enables machine learning practitioners to experiment with various algorithms for detecting intrusions, including Denial of Service (DoS), unauthorized access, probing, and other types of network attacks.

## Dataset Files

The following files are included in this folder:

1. **kddcup.data.corrected.csv**  
   - This is the full dataset, containing labeled records of network traffic (both normal and various attacks).
   - **Size:** ~725 MB (compressed in `.gz` format, it may vary slightly depending on compression).

2. **kddcup.data.gz**  
   - The compressed version of the full KDD Cup dataset.
   - **Size:** ~17 MB (compressed).
   
3. **kddcup.data_10_percent.csv**  
   - A 10% subset of the original dataset, widely used for quicker model development and testing.
   - **Size:** ~73 MB (compressed in `.gz` format).

4. **kddcup.data_10_percent.gz**  
   - The compressed version of the 10% subset.
   - **Size:** ~2 MB (compressed).

## Dataset Dimensions

- **Full Dataset** (`kddcup.data.corrected.csv`):
  - **Dimensions**: 4,898,431 records, each with 42 features.
  
- **10% Dataset** (`kddcup.data_10_percent.csv`):
  - **Dimensions**: 494,021 records, each with 42 features.

Each record contains 41 input features describing various aspects of the network connection and a label indicating if the connection was normal or a specific type of attack.

## Download Link

If you would like to download the original datasets directly, they are available from the UCI Machine Learning Repository:

- [KDD Cup '99 Dataset on UCI Repository](https://kdd.ics.uci.edu/databases/kddcup99/kddcup99.html)

## Instructions for Use

To ensure the project works correctly, please follow these steps:

1. **Extract the Compressed Files**  
   - Extract `kddcup.data.gz` and `kddcup.data_10_percent.gz` to obtain the uncompressed `.csv` files.
   
2. **Rename Extracted Files (if necessary)**  
   - Ensure that after extraction, the files are named as follows:
     - `kddcup.data.csv` for the full dataset
     - `kddcup.data_10_percent.csv` for the 10% subset
  
3. **Verify Folder Structure**  
   - Make sure the extracted `.csv` files are placed in this same folder without further compression.
   - This step is essential for smooth functionality, as the project scripts expect these files in `.csv` format in this directory.

## Dataset Overview

The KDD Cup '99 dataset contains features that describe various aspects of network connections, such as:

- **Basic features**: Attributes derived from packet headers without inspecting the payload, including duration, protocol type, and service.
- **Content features**: Attributes like count of failed logins, indicating suspicious patterns within a connection.
- **Traffic features**: Statistical features computed over a time window, capturing metrics like the number of connections to the same host.

Each record is labeled either as "normal" or with a specific type of attack (e.g., **DoS**, **Probe**, **R2L**, **U2R**). This diversity makes it a valuable dataset for intrusion detection research and model training.

## Important Notes

- **File Extraction Requirement**: Please ensure all compressed files (`.gz`) are extracted, and the resulting `.csv` files are placed in this directory for the code to function properly.
- **Processing Time**: The full dataset is large and may take time to process. For rapid development, consider using the 10% subset (`kddcup.data_10_percent.csv`).
