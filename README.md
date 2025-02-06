# Single-Hand Gesture Recognition using OpenCV and KNN

## Overview
This project implements a single-hand gesture recognition system using OpenCV and the K-Nearest Neighbors (KNN) algorithm. The goal is to classify static hand gestures for applications such as human-computer interaction, accessibility tools, and virtual reality interfaces. The project is based on research evaluating KNN's effectiveness in recognizing 12 different gestures.

## Features
- **Real-time Hand Tracking**: Uses OpenCV and MediaPipe to detect hand landmarks.
- **KNN-based Classification**: Implements KNN for classifying static hand gestures.
- **Preprocessing Techniques**: Includes rotation and scaling adjustments to improve recognition accuracy.
- **Customizable Distance Metrics**: Evaluates different distance metrics, including Chebyshev, Euclidean, and Manhattan.

## Implementation Details

### Hand Landmark Detection
The project utilizes MediaPipe to extract 21 hand landmarks as input features. Each landmark is represented as (x, y) coordinates relative to the wrist (node 0).

### Preprocessing Steps
1. **Rotation Normalization**: A line is drawn between the wrist (node 0) and the middle finger base (node 9). The entire hand is rotated so this line is vertically aligned.
2. **Scaling Adjustment**: The hand is resized based on the distance between nodes 0 and 9 to maintain uniform proportions.

### KNN Classifier
- The extracted features are fed into a KNN classifier.
- The optimal value of K is determined through experimentation (K=3 was found to be optimal).
- Different distance metrics (Chebyshev, Euclidean, Manhattan) are tested for classification accuracy.

## Performance Analysis
- **Accuracy**: The model achieved an average accuracy of 93%.
- **Best Distance Metric**: Chebyshev distance outperformed Euclidean and Manhattan distance.
- **Misclassifications**: Gestures like “Thumbs Up” and “Thumbs Down” had lower accuracy due to similar finger placements.

## Future Improvements
- Extend to dynamic gesture recognition.
- Improve preprocessing to handle occlusions and lighting variations.
- Explore deep learning models for comparison.

## References
- [MediaPipe Documentation](https://developers.google.com/mediapipe)
- [Original Research Paper on KNN for Gesture Recognition](https://people.eecs.berkeley.edu/~jrs/meshpapers/LorensenCline.pdf)

