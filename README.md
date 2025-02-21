# Fire Detection Project
The importance of using a [fire detection alert system](https://ejsit-journal.com/index.php/ejsit/article/view/410), compared to traditional systems, lies in its advanced capabilities to provide early and accurate warnings, significantly reducing the risk of fire-related damage and casualties. Unlike conventional systems that may rely on manual detection or less sensitive technologies, modern fire detection systems utilize advanced sensors and algorithms to identify potential threats in real-time. This allows for quicker response times, enabling occupants to evacuate safely and emergency services to intervene before the situation escalates. Additionally, these systems can be integrated with smart building technologies, offering remote monitoring and automated responses such as activating fire suppression systems or notifying authorities. By leveraging such innovations, fire detection alert systems not only enhance safety but also minimize property loss, making them a critical upgrade over traditional methods.
## Models

This project aims to develop a highly accurate fire detection system using [**convolutional neural networks (CNNs)**](https://www.geeksforgeeks.org/introduction-convolution-neural-network/) and compare its performance with popular architectures such as [**AlexNet**](https://medium.com/@siddheshb008/alexnet-architecture-explained-b6240c528bd5), [**VGGNet**](https://medium.com/@siddheshb008/vgg-net-architecture-explained-71179310050f), and [**ResNet**](https://medium.com/@siddheshb008/resnet-architecture-explained-47309ea9283d). It also includes real-time detection functionality and model evaluation tools.

### 1. CNN-MODEL :
The architecture of a convolutional neural network (CNN) model designed for fire detection. The model takes input images of size 224x224 with 9 channels.
### Input Layer
- **Input Dimensions** : `(None, 224, 224, 9)`, where `None` represents the batch size.

### Convolutional Layers (`conv2d`)
1. **First Convolutional Layer** :
   - **Number of Filters** : 32
   - **Activation Function** : ReLU
   - **Output Dimensions** : `(None, 222, 222, 32)`

2. **Subsequent Convolutional Layers** :
   - **Number of Filters** : 64, 120, 256
   - **Activation Function** : ReLU
   - **Gradual Reduction of Spatial Dimensions**

### Batch Normalization (`batch_normalization`)
- Applied after each convolutional layer to normalize activations, improving training stability and speed.

### Max Pooling Layers (`max_pooling2d`)
- Reduce spatial dimensions by selecting the maximum value within each pooling window.
- Help reduce computational load and prevent overfitting.

### Flatten Layer (`flatten`)
- Converts the 3D output of the last pooling layer into a 1D vector of size 36864, preparing it for fully connected layers.

### Dense Layers (`dense`)
1. **Two Dense Layers** :
   - **Units** : 256
   - **Activation Function** : ReLU
   - **Learn complex patterns in the data**

2. **Dropout Layers** :
   - Included after each dense layer to avoid overfitting by randomly deactivating a fraction of input units during training.

### Output Layer (`dense_2`)
- **Units** : 1
- **Activation Function** : Sigmoïde
- **Suitable for binary classification tasks like fire detection**

## Usage

To use this model, follow these steps: :

1. Clone this repository
2. Install the required dependencies.
3. Load the training and test data.
4. Train the model using the provided script.
5. Evaluate the model's performance on the test data.

## Features

🔥 Fire Detection: A custom CNN model optimized through multiple modifications for robust fire detection.

📊 Model Comparison: Implementation of AlexNet, VGG, ResNet to compare with the custom CNN model.

📈 Model Evaluation: Tools to evaluate models using images and real-time video streams.

⚡ Real-Time Detection: Fire detection in live video streams using OpenCV and TensorFlow.

## DATASET

🗂 www.kaggle.com/datasets/anhalayoub/fire-data

## Dependencies

- `TensorFlow`
- `Keras`
- `NumPy`
- `Matplotlib`
