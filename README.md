# Face Detection using python and Dlib/Face_recognition

__It contains 3 parts__

## 1. Gettings the data/Images from google image search
  A file name "**ImageDownload.py**" will donload the image from google and store it in you local hard drive in Current working directory
  you can use the comand line arguments to specify which player image you want and how much images you want to download
  i.e run this command 
  
          python ImageDownload.py --peopleList 'Albert Einstein','Nicola Tesla' --limit 5 
          
   : -- peopleList argument expects list of peoples' images. you can specify single iamge or multiple seperated by comma.
   
   : -- limit argument specifies how many images to download. here it will downlload 5 images for each person (i.e. Albert Einstein and Nicola Tesla)

The Data gets stored in the Folder structure format as follows :
Parent Direcotry : 
FacesDB : 

---- Albert Einstein-- 5 images 

---- Nicola Tesla -- 5 images
   
all the images of people will be stored under FacesDB folder as shown here: (https://github.com/VaibhavKhamgaonkar/FaceDetection/blob/master/Screen%20Shot%202018-06-29%20at%202.56.38%20PM.png)
* the next operation performed on the images is to crop the specific face area and replace the originial image. The command will take care of that thing as well. so finally you have al lthe face data created on your hard drive in working directory.


### Note: If you are tying to get more than 100 images then you need have **chrome driver** and you need to update the file at for chrome driver path( I have added mine ) you will have to change that. Just google it for chrome driver you will get it.

## 2. Training the Data

* Once the Data is availbale. You can simply run the belwo command which will start the training. Training mainly involved in identifying **68 facial Key points**, affining them to suitable shape and then extracting the **face embeddings (128 facial features)**.
* After getting the features the data is then fed to **SVM model for training.** 

* I have used the face_recognition api to do this stuff.

* After training is over the model gets saved into your local drive at the **Encoding_Data/** folder.
        
      python FaceTraining.py


## 3. Testing the Program

* Once the training is done we are ready to test the model on youtube streaming videos.
* To test it get the youtube video url from youtube and pass it as an agrument to **Main.py file**

      python Main.py --url 'https://youtu.be/t27OqUlCSOg' --thresh 0.7
      
* Thats it ...! The video will get played and faces will get identified automatiaclly. Also the video will get stored on current working directory.

* you can change the threshold values as per your requirement.

=========================**ALL DONE** ===============================

# Dependencies 

* The following packages shouldbe installed on your system before running the scripts

1. Open cv (Cv2) 3.4
2. dlib
3. pickle
4. pafy and youtube_dl for streaming youtube videos
5. imutils
6. face_recognition (pip install face_recognition) https://pypi.org/project/face_recognition/
7. google_images_download (pip install google_images_download) https://pypi.org/project/google-images-download/1.0.1/ for downloading the images from google.
8. numpy

===========xxxxxxxxxxxxxx=================
