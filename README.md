# ML-Assisted Latency Prediction in 5G XHaul Networks

This repository contains the source code, dataset subset, and notebooks associated with my master's thesis:  
**"Machine Learning-Assisted Prediction in Packet-Switched 5G XHaul Networks"**

## Overview

Modern 5G networks rely on deterministic latency estimators to control flow admission in the fronthaul and midhaul (XHaul) segments. While safe, these estimators are often overly conservative, leading to unnecessary flow rejections.

This project explores the use of machine learning (ML) models to predict whether a network flow would meet the Service Level Agreement (SLA), allowing for more adaptive and efficient admission control.

## Models Used

Three classifiers were trained and evaluated:

- Logistic Regression (LR)
- Random Forest (RF)
- Multi-Layer Perceptron (MLP)

Each model was tuned and tested using cross-validation, threshold optimization, and cost-sensitive evaluation metrics.

## Key Features Used

The most relevant features used during training were:

- `flowTypeId`
- `bitrate`
- `burstSize`
- `latLimit`
- `hops`
- `latWCmodel`

These features were selected for their predictive value, low redundancy, and availability at inference time.

## Results

- ML-based admission controllers consistently outperformed the worst-case estimator.
- False negatives (critical SLA violations) were reduced significantly, especially under Random Forest and MLP models.
- The system remained robust under stress scenarios and maintained high accuracy even with stricter latency constraints.

## How to Run

1. Clone the repository
2. Create the environment:
   ```bash
   conda env create -f env/environment.yml
   conda activate xhaul-thesis
3. Open the Jupyter notebook and run all cells:
   ```bash
   jupyter notebook notebook/thesis_final_analysis.ipynb

## License

This project is licensed under the MIT License. See LICENSE for more information.

