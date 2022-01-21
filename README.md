# miniproject
Steps Involved to implement Smile Detection and Selfie Capture Project

We first import the openCV library.
Now start webcam in the second line using the VideoCapture function of cv2.
Then, include haarcascade files in the python file.
Video is nothing but a series of images so we will run an infinite while loop for the same.
Then we are reading images from the video through read().
As feature recognition is more accurate in gray images we will convert the image to gray image using cvtColor() and BGR2GRAY which are basic openCV functions.
Now we will read faces using an already included haarcascade file and detectMultiscale() function where we pass gray image, ScaleFactor, and minNeighbors.
ScaleFactor: Parameter specifying zoom image, accuracy depends on it so we will keep it close to 1 but not very close as if we take 1.001(very close to 1), then it would detect even shadows so 1.1 is good enough for the face.
minNeighbors: Parameter specifying how many neighbors each rectangle should have to retain it.
If it detects a face we will draw an outer boundary of the face using rectangle() method of cv2 containing 5 arguments: image, initial point (x, y), an endpoint of principal diagonal (x + width, y + height), color of the rectangular periphery and last parameter is the thickness of drawn rectangular periphery.
If the face is detected then we will similarly detect a smile and if a smile is detected too we will print Image<cnt> saved in the cmd/terminal and then we have to provide the location of the folder in which we want to save the images.
To save the images we will use imwrite() which takes 2 parameters- location and image.
To prevent memory overflow we will just save 2 images in one run and thus useif statement which breaks the loop if cnt>=2.
To break infinite loop, we have used an if statement which becomes true when we press ‘q’ denoting ‘quit’.
At last, we will release the video.
Do not forget to destroy all the windows.
  ![2022-01-18](https://user-images.githubusercontent.com/98179331/150571992-c710d8d7-bd34-422b-a628-48ef1798cdb8.png)
