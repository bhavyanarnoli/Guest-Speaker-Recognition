# Guest-Speaker-Recognition
[Report](ML_Group_10.pdf) enlists the report of all the things done 

## Problem Statement
Given an audio identify the speaker from the following: Benjamin Netanyau , Jens Stolensberg, Julia Gillard , Margaret Tarcher, Nelson Mandela

### Link to dataset: [link](https://www.kaggle.com/datasets/kongaevans/speaker-recognition-dataset)

### Dataset Description : 
Background Noise folder along with sound of 5 speaker , have to identify the speaker of the audio.
Classes are balanced  ( 1500 audio files in each class ) 

### Audio Augmentation

- Time Stretching: Time stretching is employed to alter the duration of audio signals, creating temporal variations.

- Background Noise: Background noises are added using audiomentations, introducing the noises given to us inside the ‘_background_noises_’ folder.

- Gaussian White Noise: Gaussian white noise is added to simulate random noise, enhancing resilience to unexpected sound conditions, making model robust.

- Other Speaker Voices as Noise: The other speaker voices are added as a background noise, providing additional diversity in the dataset.

### Feature Extraction

#### MFCC : 
Represents the short-term power spectrum, emphasizing perceptually relevant frequency components.
Involves framing the signal, windowing, FFT computation, processing through a Mel filter bank, logarithm, and DCT application.
Provides a compact representation capturing overall spectral characteristics for analysis.

#### Delta MFCC : 
Captures changes in spectral characteristics over time, offering insights into speech spectrum evolution.
Provides a dynamic representation of a speaker's voice by focusing on subtle changes in speech dynamics.
Helps differentiate unique voice features accurately for speaker recognition.

#### Delta Delta MFCC: 
Complements Delta MFCC by capturing acceleration in changes to vocal characteristics.
Enhances system precision in capturing variations in speech of different speakers by addressing changes and accelerations.

#### LDB: 
Quantifies energy distribution across frequency bands, enhancing discriminatory power in speaker recognition.
Analyzes specific frequency regions in the frequency domain.


#### Result

Testing and Model Selection
Data Splitting → Testing has been performed on augmenting the 20% split of clean data.
Features considered → MFCC, Delta MFCC, Delta Delta MFCC, LDB.
Training → The model was trained on combination of 80% of  data by augmenting it along with it’s own features.

Model Performances: 
Model-1: GMM - Features {mfcc, delta mfcc, ldb}, Accuracy {84.4%} [code](GMM_Models) GMM model code and result
Model-2: SVM(RBF Kernel) - Features {mfcc, delta mfcc, ldb}, Accuracy {97.33%} [code](SVM_Models) SVM model code and result 

Model-3: GMM - Features {mfcc, delta mfcc , delta delta mfcc}, Accuracy {99.08%}



