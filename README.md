# EEG Signal Processing for Seizure Detection using Deep Learning on CHB-MIT-eeg-dataset-seizure-detection

## Introduction

This repository contains the code and methodology for detecting seizures from EEG data using deep learning techniques. The project focuses on improving seizure detection accuracy by processing raw EEG signals and applying deep learning architectures like Convolutional Neural Networks (CNN) and Residual Networks (ResNet).

## Dataset

We utilized EEG recordings in **EDF** (European Data Format) files. The dataset contains 664 EDF files from patients, each labeled with seizure and non-seizure events. The data has been processed to ensure that each case has at least two seizures, though the seizure types are unspecified.

## Preprocessing Steps

The following steps were carried out to prepare the data for deep learning model training:

1. **Selection of Files:**  
   Only EDF files containing at least one seizure event were selected for further processing.

2. **Shortening Recordings:**  
   Each EEG recording was truncated to 10 times the seizure duration before and after each seizure event to focus on critical segments.

3. **Balanced Dataset Creation:**  
   A balanced dataset was created by maintaining a 20:1 ratio of non-seizure to seizure data. For every second of seizure data, 20 seconds of non-seizure data were included.

4. **EEG Montages:**  
   We utilized 18 bipolar EEG montages to create a robust representation of brain activity.

5. **Notch Filtering:**  
   A notch filter was applied to remove 60 Hz line noise, improving the quality of the EEG signals for subsequent analysis.

6. **Feature Windowing:**  
   The model estimates seizure probability using the past 32 seconds of recording. For input to the deep learning model, a 4-second window of EEG data is used.

## Model Architecture

We initially implemented a Convolutional Neural Network (CNN) for feature extraction from the EEG signals. Later, we transitioned to a Residual Network (ResNet) architecture to leverage its deeper structure and ability to handle vanishing gradient problems, improving performance.

### Key Model Characteristics:
- **Input:** Past 4 seconds of EEG data.
- **Feature Extraction:** The CNN (or ResNet) learns high-level features from the EEG signals.
- **Probability Estimation:** The model predicts the probability of a seizure based on the extracted features.

## Results

Our approach has shown promising results in seizure detection. We expect improvements as we continue refining the model architecture and hyperparameters.

## Future Work

- **Further Model Tuning:**  
   Hyperparameter optimization and model tuning to improve accuracy.
   
- **Additional Data Sources:**  
   Incorporation of more diverse datasets, possibly including seizure type classification.

## Conclusion

This repository presents a robust framework for seizure detection using EEG data. By combining data preprocessing, feature extraction, and advanced deep learning techniques, this project aims to enhance seizure detection accuracy and reliability.

## Acknowledgments

We would like to acknowledge the use of the HMS and CBMIT datasets from Kaggle for model training and experimentation.
