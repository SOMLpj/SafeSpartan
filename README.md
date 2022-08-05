# SafeSpartan
Senior Project SJSU SUMMER 2022

Safe Spartan is a machine learning based project that predicts crime (frequency & type) on San Jose State University Campus. This is accomplished by first training a GAN model on crimes in the city of San Francisco. The training took place for January through December 2021. Each month was trained three times with three different crimes: Theft, Assault, Violent/Other (where Other represents homicide, rape, and missing persons on campus).  

The GAN model makes a prediction based off of the inputs it was trained on. The predicted outputs are displayed on a web application to promote user interaction and to increase the usefulness of the project itself.  

The webapp allows the user to select between any of the three crimes across any of the twelve months. The combinations are computed live through a remote server function in Google Collab.  

# Understanding the output

![3](https://user-images.githubusercontent.com/29829945/182503127-0f1cbf71-f229-47c1-a882-3156d5be0b21.jpg)
![1](https://user-images.githubusercontent.com/29829945/182503104-a7acd9df-96d0-4593-b916-edb8bdec21dd.jpg)
![2](https://user-images.githubusercontent.com/29829945/182503119-3806318d-1f50-436b-9c86-19cedbeb113a.jpg)


RED: Violent/Other Crimes  
BLUE: Theft  
Green: Assault  

The brightness of the color represents the frequency of the crime. For example, predicted outputs often show little to no red squares. This means there are few violent crimes on campus. A dark green colored square however, represents a high frequency assaults.

Below is an overlay of March, May, and July assault around campus.
![image](https://user-images.githubusercontent.com/52023760/183222739-4c0295c2-1c19-4a76-82e1-0ff9c75e9b55.png)


Report: https://docs.google.com/document/d/18FzZny6VXcsMVf4wMmMWe3eoieKea6krHSk29qvhUCA/edit?usp=sharing

# 1. Setting up Google Collab
First, you will need to make a copy of the [google collab](https://colab.research.google.com/drive/1ZfMaTHpJIlS5tmKq2Vk4sNsw48_3ZTcS?usp=sharing).
Once you have a copy, you will need to provide training data and adjust the path to your directory accordingly.
For our project, we used a shared google drive to host the file. The collab instance will be able to sign in and view the files.


# 2. Gathering and cleaning data
In our project, we used data from the San Francisco Government. This was used because it was readily availiable and in a clean format with coordinates.
Download whichever CSV files you like. Make sure they have Latitude and Longitude as a column in the data. Place all files into your path and make sure collab is able to find it. At the bottom of the collab, there is a section titled "Matplotlib heatmap". In this section you will find scripts to clean up the data into a format that the model can use.

Once the data has been cleaned, they will be renamed and placed in the same directory. The next few cells will use matplotlib functions to generate a heatmap of the area. Save the image as a 256 x 256 image.

In order to have a visual reference, use Google maps around the area you are collecting data. In this, you will be able to collect coordinates. Use these coordinates to filter the range of the heatmap. The variable titled point1 is the top left, and point2 is the bottom right. Using this standard will allow us to create neat squares of maps. Save the map as a 256 x 256 image within the two points that you have selected.

Once you have a heatmap and a google maps image, combine the two using a program of your choice. Make sure the final image has a dimension of 512 x 256

Be sure to change the BUFFER_SIZE to the amount of images that you have in your dataset.

Make sure that your training images and testing images are separate. The model is trained on the images, and the test set is used to compare. Keep them in separate folders.

# 3. Running the model
By this stage, you should have the collab running, your google drive connected, and proper paths to your files. Now you will just need to run the fit function for the amount of steps you desire. With a pro instance of google collab, it took approximately 60 seconds per 1000 steps. An image is generated every 1000 steps. We trained our 36 various models over the course of about 13 hours. For free users, try smaller data sets or less steps.

# 4. Generating output
Once you model is trained, see the training images sections. This will create images based on what the model has learned. It only takes in to account the input image, and the ground truth is used for a reference.
