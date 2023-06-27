## 3DFER_SE4AI
The 3DFER project uses Facial Emotional Recognition through artificial intelligence algorithms to detect and interpret human emotions.

## Description
3DFER uses machine learning algorithms to train a deep neural network model capable of recognizing emotions in facial images. 2D models were created as a reference for the 3D models (whose dataset is created through reconstruction) in order to highlight the performance differences between them.

## 🗃 Dataset
The dataset used is [FER2013](https://www.kaggle.com/datasets/msambare/fer2013), which consists of grayscale images of size 48x48 and provides annotations on emotions with 7 different classes: "Angry," "Disgust," "Fear," "Happy," "Sad," "Surprise," and "Neutral." 
[FER2013](https://www.kaggle.com/datasets/msambare/fer2013) is divided into 28,709 examples for the training set and 3,589 examples for the test set. 
The data from  [FER2013](https://www.kaggle.com/datasets/msambare/fer2013) has been transformed [here](3DTransformation) to apply the 3D models. If you want to apply it, you need to apply [LandmarkExtraction](3DTransformation/LandmarkExtraction.ipynb) first and then [LandmarkVoxelization](3DTransformation/LandmarkVoxelization.ipynb).

## 💡 Models
The created models have been divided into [2D](models/2DModels) and [3D](models/3DModels), and for each model, the data has been loaded from Google Drive. If necessary, you can modify the code snippet and insert the appropriate path. MLflow was used to track the data obtained from the models. If you don't want to use it, you should not execute the MLflow installation code snippets and comment out the start_run parts in the model training cells.

## 🚧 To-Do
- [ ] Mesh CNN

Feel free to contribute to this project! We welcome any contributions, suggestions, or improvements. Open a pull request or submit an issue.
