Heartbeat Sound Classification Using CNN
Overview

This project focuses on developing a convolutional neural network (CNN) to classify heartbeat sounds as either normal or abnormal. By extracting Mel-frequency cepstral coefficients (MFCCs) from audio recordings of heartbeats, the model learns to distinguish between healthy and pathological heart sounds. The system is designed for potential use in automated medical diagnostics, assisting in the early detection of cardiovascular abnormalities.
Objectives

    Feature Extraction: Extract MFCCs from heartbeat audio files to capture spectral characteristics relevant to heart sound classification.
    Model Development: Construct a 1D CNN to perform binary classification (normal vs. abnormal heartbeats).
    Evaluation: Evaluate the model's performance using accuracy metrics on a test dataset.
    Application: Support medical professionals in screening for heart conditions through non-invasive audio analysis.

Dataset

The dataset used is the Heartbeat Sounds dataset, available on Kaggle: Heartbeat Sounds.
Dataset Details

    Source: Publicly available heartbeat sound recordings, primarily from the PhysioNet/Computing in Cardiology Challenge 2016.
    Content: Contains audio files of heartbeat recordings, divided into two categories: normal and abnormal.
        Normal: Heart sounds from healthy individuals.
        Abnormal: Heart sounds indicating potential cardiovascular issues (e.g., murmurs, extra sounds).
    File Format: WAV files with varying sample rates, resampled to 22,050 Hz for consistency.
    Structure: Files are labeled with prefixes indicating their category (e.g., normal__*.wav or abnormal__*.wav).
    Size: Includes 176 audio files in set_a (used in this project), with a mix of normal and abnormal recordings.
    Usage: Audio files are processed to extract MFCC features for classification.

Preprocessing

    Audio files are loaded and resampled to a uniform sample rate of 22,050 Hz.
    MFCC features (40 coefficients) are computed using the librosa library, and the mean of the transposed MFCC matrix is taken to create a fixed-size feature vector per file.
    Labels are assigned based on filenames: 0 for normal, 1 for abnormal.
    Features are normalized and reshaped to fit the 1D CNN input requirements.

Methodology

    Data Loading: Load heartbeat audio files from set_a and extract MFCC features.
    Data Preparation: Compute mean MFCCs for each file, convert features and labels to NumPy arrays, and split into training (80%) and test (20%) sets.
    Model Architecture: A 1D CNN with a single convolutional layer (32 filters, kernel size 3), max-pooling, flattening, a dense layer (64 units), dropout (0.5), and a sigmoid output layer for binary classification.
    Training: Train the model for 10 epochs using the Adam optimizer and binary cross-entropy loss.
    Evaluation: Assess model performance on the test set, reporting accuracy.
    Output: Display test accuracy as a percentage.
    Tools and Libraries

    Python Libraries: Librosa (for audio processing and MFCC extraction), NumPy (for array operations), Scikit-learn (for train-test splitting), Keras (for CNN implementation).
    Hardware: Standard CPU/GPU for model training.

Expected Outcomes

    A trained 1D CNN model capable of distinguishing normal from abnormal heartbeat sounds with reasonable accuracy.
    Validation of MFCCs as effective features for heartbeat sound classification.
    A foundation for automated heart sound analysis in clinical settings.
