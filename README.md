# QUANTUM-ENHANCED ORAL DISEASE DETECTION USING HYBRID QUANTUM-CLASSICAL NEURAL NETWORKS

<img width="4608" height="3456" alt="1" src="https://github.com/user-attachments/assets/252d66a2-aeeb-42f2-a24f-dc16d57e6bf8" />

<img width="4608" height="3456" alt="2" src="https://github.com/user-attachments/assets/65b24aec-f7c0-4167-8e58-6b331dfe7302" />

QUANTUM-ENHANCED ORAL DISEASE DETECTION USING HYBRID QUANTUM-CLASSICAL NEURAL NETWORKS

Almost half of the world's population has oral diseases, but it is still very challenging to identify them early and accurately. Traditional deep learning techniques frequently necessitate extensive labeled datasets and encounter challenges related to noise, overlapping anatomical structures, and overfitting. We were interested in quantum machine learning (QML) for medical imaging, so we wanted to see if hybrid quantum-classical neural network models could improve oral disease diagnostics by giving us results that were more accurate, easier to understand, and more useful.

What it does

We use Hybrid Quantum-Classical Convolutional Neural Networks (HQCNN) and Quantum Convolutional Neural Networks (QCNN) to sort images of oral diseases like dental calculus and hypodontia.

Our results show that with an accuracy of 88.73%, HQCNN exceeded QCNN in binary
classification. With a top accuracy of 65.92% utilizing a 3-qubit architecture, HQCNN displayed decent performance for multi-class classification.

Furthermore, the HQCNN, which has a ResNet18 backbone and a 2-qubit quantum layer, achieves an accuracy of 99.8%.

 With an 8-qubit, 100-epoch QCNN, it registered a lower accuracy of 68.75% in binary classification. Additionally, QCNN, which has 8 qubits and quantum pooling, got about 72% accuracy after applying the preprocessing technique.

Both do better than classical CNNs, showing that quantum-enhanced diagnostics could be useful. These models demonstrate that quantum feature extraction, even with a limited number of qubits, can improve generalization and decrease the number of parameters.

How we made it

We used the Kaggle oral disease dataset (calculus and hypodontia). We applied preprocessing techniques such as resizing and normalization, along with augmentations such as flipping, rotating, and Gaussian blur.

HQCNN:

ResNet18 feature extractor → dimension reduced to 2 → fed into a 2-qubit parameterized quantum circuit with Ry + CNOT gates. PyTorch autograd is combined with the HQCNN for mixed optimization.

QCNN:

Used PCA + ZFeatureMap to turn 16×16 grayscale images into 8 qubits. 
Made layers of quantum convolution and pooling that switch back and forth in Qiskit.

Training:

We used the Adam optimizer to schedule the learning rate.
We used a 5-fold cross-validation method with early stopping.
Accuracy, precision, recall, F1, and AUROC are used to evaluate.
The cloud setup involved using Google Colab with a Tesla K80 GPU and Qiskit AerSimulator for the quantum layers.

Things that were hard for us

The data encoding bottleneck is the process of mapping high-dimensional dental images into a small number of qubit states.
Noise affected the training of variational circuits.
Simulation overhead: HQCNN took longer to run than CNN.
Interpretability: It was challenging to fill in the "black box" gap, so we used Grad-CAM and LIME to make things clearer.

Things we've done that we're proud of

This is the first time that HQCNN (which has a ResNet18 backbone and a 2-qubit quantum layer) has been used to diagnose oral diseases. 
It got 99.8% accuracy, which is better than the CNN and QCNN baselines.
Successfully showed that heatmaps can be used to interpret data, allowing dentists to check model predictions visually.
Created a framework that can grow and be used for other medical imaging tasks.

What we found out

Quantum layers can greatly improve feature learning while using fewer parameters.
In real-world datasets, hybrid designs often work better than pure quantum designs.
In healthcare AI, being able to understand is just as important as being accurate.
Quantum models appear promising, but hardware issues remain a significant challenge.

What comes next for quantum machine learning in dental diagnostics?

Add more classes, like gingivitis, caries, and oral cancer.
Go from simulations (Qiskit Aer) to real quantum hardware.
Make circuits that can handle noise and new ways to encode data.
Work with dentists to make sure that it works in real-life clinical settings.
