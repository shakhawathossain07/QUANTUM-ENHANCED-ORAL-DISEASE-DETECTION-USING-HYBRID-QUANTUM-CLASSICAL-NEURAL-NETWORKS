# Quantum Machine Learning in Dental Diagnostics

<img width="4608" height="2492" alt="1" src="https://github.com/user-attachments/assets/9b7c9f1f-f77f-4315-94f5-608d19e255e6" />


<img width="4608" height="3456" alt="2" src="https://github.com/user-attachments/assets/d63de26f-e573-4d06-9341-6050cb48bd04" />


01. ABSTRACT

Around the half of the population in the world are affected by oral diseases, making it one of the
most common health conditions. Quantum implementation in medical domain has revealed its
potential and versatile applicability especially in medical imaging. This paper explores oral disease
identification using hybrid quantum-classical neural networks (HQCNN) and quantum convolution
neural networks (QCNN). Our work investigates the possibilities of quantum machine learning in
processing complicated dental image data and the contributions it can make in oral healthcare. We
implemented a hybrid and a pure QNN leveraging Qiskit framework and a whole dataset of annotated
oral disease dataset. Our 8 qubit structured QCNN model and 2 qubit architecture of HQCNN model
extract the image features by encoding the features into quantum circuits enabling more expressive
demonstration employing fewer parameters. The final result showcases that QCNN and HQCNN
perform better than CNNs in disease classification and promise better accuracy, generalization and
computational efficiency. This experiment highlights a pioneering step in applying quantum inspired
models for oral diagnostics, identifying promising avenues for improving oral healthcare worldwide.

02. OBJECTIVE

1. To make sure the dataset was optimum for training quantum models, a varied collection of
oral disease photos was gathered and preprocessed using rotation, shape, scaling, and splitting.
ADASYN was used to correct imbalanced classes.
2. Two novel quantum architectures, the Hybrid Quantum-Classical Neural Network (HQCNN)
and the Quantum Convolution Neural Network (QCNN), were created and put into use with
the express purpose of identifying images of oral diseases.
3. To improve model performance and interpretability, a novel "GrandCam Decision
Boundaries" method—possibly a custom visualization or decision-making technique—was
added, along with integrated PCA for dimensionality reduction and angle encoding for quantum
state preparation.
4. Tested the performance of HQCNN and QCNN using a preprocessed dataset to identify the
most efficient model for oral disease categorization.
5. Emphasized the possibilities of quantum machine learning in medical imaging since quantum
models stand out in managing high-dimensional data and extracting complex features

03. METHODOLOGY
  
 Preparing Data:
 Dataset: A set of dental photos from Kaggle that depict different oral conditions (such as cavities and discolouration).
 Data Preprocessing: Class balancing with ADASYN and data augmentation (rotation, flipping, scaling, and noise
 addition).
 Dimensionality Reduction & Angel Encoding: Dimensions are reduced using Principal Component Analysis (PCA),
 and the features that are produced are scaled for angle encoding in quantum circuits.
 Model Structures:
 HQCNN: Combines a quantum layer with traditional convolutional layers. The foundation of the quantum layer
 consists of parameterized quantum circuits that enable backpropagation via parameter shift rules (by employing RY
 rotation gates and σz measurements).
 QCNN: Reduces the dimensionality of the quantum state prior to measurement by applying alternating quantum
 convolutional and pooling layers after encoding images into quantum states using a feature map (such as Qiskit's
 ZFeatureMap).
 Training Specifics:
 Optimization: Cross-entropy loss optimizers such as Adam (for HQCNN) and COBYLA (for QCNN) are used to train both
 models.
 Architectural Tuning: Various quantum encoding methods are tested, together with variations in the number of qubits
 and circuit depth
