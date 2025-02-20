# Fire Detection Project
The importance of using a [fire detection alert system](https://ejsit-journal.com/index.php/ejsit/article/view/410), compared to traditional systems, lies in its advanced capabilities to provide early and accurate warnings, significantly reducing the risk of fire-related damage and casualties. Unlike conventional systems that may rely on manual detection or less sensitive technologies, modern fire detection systems utilize advanced sensors and algorithms to identify potential threats in real-time. This allows for quicker response times, enabling occupants to evacuate safely and emergency services to intervene before the situation escalates. Additionally, these systems can be integrated with smart building technologies, offering remote monitoring and automated responses such as activating fire suppression systems or notifying authorities. By leveraging such innovations, fire detection alert systems not only enhance safety but also minimize property loss, making them a critical upgrade over traditional methods.
## Models

This project aims to develop a highly accurate fire detection system using [**convolutional neural networks (CNNs)**](https://www.geeksforgeeks.org/introduction-convolution-neural-network/) and compare its performance with popular architectures such as [**AlexNet**](https://medium.com/@siddheshb008/alexnet-architecture-explained-b6240c528bd5), [**VGGNet**](https://medium.com/@siddheshb008/vgg-net-architecture-explained-71179310050f), and [**ResNet**](https://medium.com/@siddheshb008/resnet-architecture-explained-47309ea9283d). It also includes real-time detection functionality and model evaluation tools.

### 1. CNN-MODEL :
L'architecture d'un modèle de réseau de neurones convolutifs (CNN) conçu pour la détection de feu. Le modèle prend en entrée des images de taille 224x224 avec 9 canaux.
### Couche d'Entrée
- **Dimensions d'entrée** : `(None, 224, 224, 9)`, où `None` représente la taille du lot.

### Couches Convolutives (`conv2d`)
1. **Première couche convolutive** :
   - **Nombre de filtres** : 32
   - **Fonction d'activation** : ReLU
   - **Dimensions de sortie** : `(None, 222, 222, 32)`

2. **Couches convolutives suivantes** :
   - **Nombre de filtres** : 64, 120, 256
   - **Fonction d'activation** : ReLU
   - **Réduction progressive des dimensions spatiales**

### Normalisation par Lots (`batch_normalization`)
- Appliquée après chaque couche convolutive pour normaliser les activations, améliorant ainsi la stabilité et la vitesse d'entraînement.

### Couches de Max Pooling (`max_pooling2d`)
- Réduisent les dimensions spatiales en sélectionnant la valeur maximale dans chaque fenêtre de pooling.
- Aident à diminuer la charge computationnelle et à contrôler le surapprentissage.

### Couche de Mise à Plat (`flatten`)
- Convertit la sortie 3D de la dernière couche de pooling en un vecteur 1D de taille 36864, le préparant pour les couches entièrement connectées.

### Couches Denses (`dense`)
1. **Deux couches denses** :
   - **Unités** : 256
   - **Fonction d'activation** : ReLU
   - **Apprentissage de motifs complexes dans les données**

2. **Couches de Dropout** :
   - Incluses après chaque couche dense pour éviter le surapprentissage en désactivant aléatoirement une fraction des unités d'entrée pendant l'entraînement.

### Couche de Sortie (`dense_2`)
- **Unités** : 1
- **Fonction d'activation** : Sigmoïde
- **Adaptée pour des tâches de classification binaire comme la détection de feu**

## Utilisation

Pour utiliser ce modèle, suivez les étapes suivantes :

1. Clonez ce dépôt.
2. Installez les dépendances nécessaires.
3. Chargez les données d'entraînement et de test.
4. Entraînez le modèle en utilisant le script fourni.
5. Évaluez les performances du modèle sur les données de test.

## Features

🔥 Fire Detection: A custom CNN model optimized through multiple modifications for robust fire detection.

📊 Model Comparison: Implementation of AlexNet, VGG, ResNet to compare with the custom CNN model.

📈 Model Evaluation: Tools to evaluate models using images and real-time video streams.

⚡ Real-Time Detection: Fire detection in live video streams using OpenCV and TensorFlow.

## DATASET

🗂 www.kaggle.com/datasets/anhalayoub/fire-data

## Dépendances

- `TensorFlow`
- `Keras`
- `NumPy`
- `Matplotlib`
