# Speaker-Identification-Classical-vs-Deep-Learning-Models
This project investigates various speaker identification strategies using both traditional machine learning and deep learning approaches. The goal was to explore how well different models can recognize speakers from short audio clips, starting from classical methods to more modern, hybrid, and sequential models.
## Datasets
1.  EmoDB (Emotional Speech Database)
   - German emotional speech dataset.
   - 10 speakers with various emotions.
   - Used for small-scale, emotion-influenced speaker identification.
2. 50 Speakers Audio Data (Kaggle)
     - Large dataset with 50 distinct speakers.
     - Clean recordings suitable for deep learning models.
## Models Explored
1. GMM (Gaussian Mixture Models)
   - Trained on MFCC features per speaker. Served as a baseline.
2. Deep Learning Models
   ### CNN1D vs CNN2D
   - Explored the effect of input shape:
      - CNN1D: Treat MFCC as sequences (time × features).
      - CNN2D: Treat MFCC as images.
   -CNN2D outperformed CNN1D due to richer spatial feature extraction.
   ### LSTM
   - Motivation: MFCCs are sequential; LSTM captures time dependencies.
   - Input: MFCCs as time sequences.

## Hybrid Models
 ### CNN+GMM
 - CNN used to extract speaker embeddings (penultimate Dense layer).
 - GMMs trained on these embeddings per speaker.
### CNN+KNN
CNN embeddings are also passed to a KNN classifier.
- **Why KNN?** Leverages **embedding separability** without distribution assumptions.
- **Observation**: Performs well when embeddings form **distinct clusters**.
- 
# Deployment with Flask
We built a simple Flask web app to demonstrate real-time speaker recognition. This app allows users to upload an audio sample (e.g., .wav file), and the trained model returns the predicted speaker identity.
## Features
- Audio upload interface

- MFCC extraction on the server

- Model inference (CNN2D)

- Display of the predicted speaker name

 







