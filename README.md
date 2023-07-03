## 3DFER_SE4AI
The 3DFER project uses Facial Emotional Recognition through artificial intelligence algorithms to detect and interpret human emotions.

## Description
3DFER uses machine learning algorithms to train a deep neural network model capable of recognizing emotions in facial images. 2D models were created as a reference for the 3D models (whose dataset is created through reconstruction) in order to highlight the performance differences between them.

## 🗃 Dataset
The dataset used is [FER2013](https://www.kaggle.com/datasets/msambare/fer2013), which consists of grayscale images of size 48x48 and provides annotations on emotions with 7 different classes: "Angry," "Disgust," "Fear," "Happy," "Sad," "Surprise," and "Neutral." 
[FER2013](https://www.kaggle.com/datasets/msambare/fer2013) is divided into 28,709 examples for the training set and 3,589 examples for the test set. 
The data from  [FER2013](https://www.kaggle.com/datasets/msambare/fer2013) has been transformed [here](3DTransformation) in order to get 3D data. If you want to use it, you need to apply [LandmarkExtraction](3DTransformation/LandmarkExtraction.ipynb) first, which gives you the train and test set in the format of 478 3D landmarks per image, and then [LandmarkVoxelization](3DTransformation/LandmarkVoxelization.ipynb), which transforms these data in a voxel mask.
With [MeshConnectivityExtraction](3DTransformation/MeshConnectivityExtraction.ipynb) we use landmarks and connection to extract faces and build meshes. This is needed to work with [DistanceCNN](models/2DModels/DistanceCNN.ipynb). If you run the code of [MeshConnectivityExtraction](3DTransformation/MeshConnectivityExtraction.ipynb), you can also use a 3D visualizer to take a look at the meshes.

## 💡 Models
The created models have been divided into [2D](models/2DModels) and [3D](models/3DModels), and for each model, the data has been loaded from Google Drive. If necessary, you can modify the code snippet and insert the appropriate path. MLflow was used to track the data obtained from the models. If you don't want to use it, don't execute the MLflow installation code snippets and comment out the relevant parts in the model training cells.
For the implementation of [VGG](models/2DModels/VGGTransferLearning.ipynb), the weights were downloaded from  [here](https://www.robots.ox.ac.uk/~albanie/pytorch-models.html).

## 📊 Results
To sum up, as expected 2D models work better than 3D models, with the best models for the 2D going over 67% accuracy, while 3D not going over 57%, but if training time is a factor, one could choose to use the latter. Better insights are reported in [the final report](3DFER_FinalReport.pdf) 

## 🚧 To-Do
- [ ] Mesh CNN
- [ ] DagsHub integration -- Please ignore the .dvc files
