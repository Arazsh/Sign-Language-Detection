# Sign-Language-Recognizer
In this code, a multi-class model is developed for recognizing sign language images using TensoFlow. The images are from the sign language dataset (https://www.kaggle.com/datamunge/sign-language-mnist/home) which are distributed among 24 classes. The developed model consists of four convolutional and two dense layers. The callbacks class is also defined to stop training after reaching to a desired accuracy. To reduce the overfitting issue, image augmentatioin is employed in the training process. The model delivers 92% of training accuracy for augmented training set after 24 epochs (92% is set in the callbacks and it can be changed), and close to 97% testing accuracy.The acuuracy and loss changes versus epochs for both training and validtion sets are plotted at the end.  
The procedure of the code is as follows:

## The myCallbacks class

After importing the required modules in the first section of the code, the myCallbacks class is defined. The instance object of this class (callbacks) is inserted into model.fit to obtain the model metrics at the end of each epoch. Using the metrics, it is possible to control the training process. In the myCallbacks, the training stops after 92% of accuracy on the train set.

## Loading the train and validation .CSV files into the notebook
Downloading the two 2 .CSV files, sign_mnist_test.csv and sign_mnist_train.csv from https://www.kaggle.com/datamunge/sign-language-mnist/home to the local machine, 
and uploading them to the notebook using files.upload().  
Then, the get_data function is defined to read the .CSV files and convert them to train/test images. Each line of the files contians 785 comma separated values between 0 and 255. The first value is the label of the sign language which is an integer between 0 and 24 (no cases for 9=J or 25=Z because of gesture motions. Therefore, there exist 24 classes). The 784 pixel values (comma separated values) are then converted to 28*28 images. Below, two example sign language, the size of train and test sets, and the label information for signs are provided. 

![alt text](https://github.com/Arazsh/Sign-Language-Recognizer/blob/media/image1.png?raw=true) 
