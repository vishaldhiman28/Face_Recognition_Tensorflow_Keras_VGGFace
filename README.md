# Face_Recognition_Tensorflow_Keras_VGGFace

This project is for Recognition of Face using the VGGFace pre-trained model. I am recognizing a total of 6 faces.

VGGFace Pre-Trained model can be found here : 
https://github.com/rcmalli/keras-vggface

Requirements to run the project:

    1. TensorFlow (Version: 1.15.0-rc3)

    2. Keras (Version: 2.2.5)

    3. Keras-VGGface (Version: 0.6)
       To install VGGFace use command in your terminal if PIP is already installed :
       --->>> pip install keras_vggface

    4. Matplotlib (Version: 3.0.3)

    5. Numpy (Version: 1.16.5)

    6. Pandas (Version: 0.24.2)

    7. Tensorflow-GPU



About Data:

I have image data of a total of six person (including me). All data is present in the Data folder.
The data folder contains three sub folder train, test and prediction images. Also, it contains one saved model(which I got after training my model on 6 classes).

6: Person are as:
   { 1: Myself (Vishal Dhiman),
     2: Christian Bale,
     3: Robert Downey,
     4: Dwayne Johnson,
     5: Bill Gates,
     6: Hrithik Roshan
   }
Both train and test folders contain 10 photos of each person in the different folders having a label with a person's name.

Prediction Images folder contains a total of six images of each person to get a prediction from the model.

How to run?

Download the Project, unzip it and then :
run command: python face_recognition.py
(keep in the mind that you have to avoid file path errors if it happens during run of program)

In cloab : 
   activate GPU and upload Data in an appropriate folder and face_recognition_jupy.ipynb to colab notebook.
   then run all cells.
   
Some Important Points about the model:

1. Loss Function: Sparse Categorical Cross-Entropy
   Since the problem is a multiclass classification problem and every person (label) is mutually exclusive of image data of others (meaning each data entry can only belong to one class). So Sparse Categorical Cross Entropy is used.
   
   This loss function is almost similar to Categorical Cross Entropy except for one change that is, we  do not need to one hot 
   encode the target vector but instead whichever the class prediction image belongs just pass the index of that class.
   
2. Model Accuracy:
   I trained the model for 50 epochs and we had very less amount of data just a total of 60 images for training and 60 for evaluation
   but the model performed very well with an accuracy of nearly 90% on evaluation data.
   I used a Keras data-generator function to generate more data from available images by shear change, zoom, and horizontal flip.
   The model can perform much more accurate if we provide more data with better quality because model accuracy can fluctuate if    
   less and noisy data is used.
