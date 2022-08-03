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

The brightness of the color represents the frequency of the crime. For example, predicted outputs often show little to no red squares. This means there are few violent crimes on campus. A dark blue colored square however, represents high frequency theft.

Below is an overlay of January Theft and SJSU campus

`IMAGE HERE`


Report: https://docs.google.com/document/d/18FzZny6VXcsMVf4wMmMWe3eoieKea6krHSk29qvhUCA/edit?usp=sharing
