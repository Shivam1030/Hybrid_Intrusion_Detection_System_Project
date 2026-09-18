# HYBRID INTRUSION DETECTION SYSTEM USING ANOMALY AND SIGNATURE-BASED TECHNIQUES

## Overview

This project implements a hybrid intrusion detection system (IDS) that combines:

•	Signature-based detection for known threats

•	Machine learning anomaly detection using a Random Forest + XGBoost ensemble

### The system introduces a confidence-aware decision mechanism with a 0.90 threshold, explicitly designed to reduce false positives and improve operational reliability. It is evaluated on the UNSW-NB15 dataset using a compact “Power 9” feature subset for efficiency and scalability.

## Features

•	Hybrid IDS framework: Signature + ML-based anomaly detection

•	Weighted RF-XGBoost ensemble with soft voting (0.6 XGBoost, 0.4 RF)

•	Confidence thresholding (0.90) to suppress uncertain predictions

•	Compact Power 9 feature set for reduced complexity and faster inference

•	Comprehensive evaluation on UNSW-NB15 dataset with strong performance metrics

## Performance Highlights

•	Accuracy: 94.6%

•	Precision: 95.8%

•	Recall: 92.3%

•	F1-Score: 94.0%

•	False Positive Rate (FPR): 1.2%

## Compared to standalone classifiers:

•	Ensemble improves F1-score by 6.2% over XGBoost alone

•	False positives reduced by 75%

## Dataset

The system is trained and tested on the UNSW-NB15 dataset, which includes:

•	2.5M network flows

•	9 attack families: Analysis, Backdoor, DoS, Exploits, Fuzzers, Generic, Reconnaissance, Shellcode, Worms


## Methodology

1.	Signature-based detection: Rule-based matching for known attacks
2.	Anomaly detection ensemble:

o	Random Forest (class_weight=balanced)

o	XGBoost (scale_pos_weight=3, GPU acceleration)

o	Weighted soft voting for final prediction

4.	Confidence thresholding:

o	Attack if probability ≥ 0.90

o	Normal otherwise

## Training Configuration

•	Random Forest: 200 estimators, max_depth=15

•	XGBoost: 300 estimators, max_depth=8, learning_rate=0.1

•	Validation: 5-fold stratified cross-validation

•	Feature Selection: Power 9 (dur, spkts, dpkts, sbytes, dbytes, sttl, dttl, sload, dload)

## Results

•	Preserves 97.8% performance of full feature set with 82% lower complexity

•	Inference time reduced by 4.7x

•	Outperforms deep learning hybrids (CNN-GRU, CNN-LSTM, CNN-RNN) in efficiency and false positive control

## Future Work

•	Real-time streaming evaluation

•	Adaptive threshold tuning based on traffic variability

•	Extension to encrypted malicious traffic and advanced persistent threats (APTs)

## References

This project builds upon prior research in hybrid IDS systems, including CNN-GRU, CNN-LSTM, CNN-RNN, ensemble methods, and domain-specific IDS approaches. Key references are included in the research paper.

## Authors

•	Shivam

•	Kushal Sharma

•	Ruprekha Behera

•	Dr. Narinder Verma

•	Akshat Shakya

•	Vivek Chaudhary

## License

### This project is released under the MIT License. You are free to use, modify, and distribute it with proper attribution.
