# faceRecog
Real time face recognition using Python

                                          INSTALLATION INSTRUCTION TO RUN FACE RECOGNITION IN REAL-TIME


NOTE: WE WILL CREATE VIRTUAL ENVIRONMENT AND INSTALL ALL DEPENDENCIES IN THAT SO THAT IT WILL NOT CHANGE/AFFECT YOUR ROOT DIRECTORY, JUST BY DELETEING THIS FOLDER YOU CAN DELETE ITS EXISTANCE.

open windows 'cmd' typing cmd in search (not conda command window) as an administrator



1) Download and install python 3.6.6 (recommended) or above from> https://www.python.org/downloads/    (if you already have then ignore this step and check its version to be sure)
NOTE: You must set path of python to home, during installation of python please tick the option present at the bottom of installation window.

2) check python version> python -V

3) Install virtual environment> pip install virtualenv
4) Test installation> virtualenv --version

5) Download folder from the drive link and extract it to 'C' drive and rename this folder to 'faceRecog', if already renamed then please ignore.
At this time if you open 'faceRecog' folder it would contains some files and folder like dataset, examples, output, videos, encodings.pickle, recognize_faces_image.py and recognize_faces_video.py

6) Now change the directroy to 'faceRecog' folder
(at this type your command prompt window should look like C:\faceRecog>)

7) create virtual environment repositery>virtualenv env
(this will create a folder with name 'env' inside working reositery 'faceRecog')

8) Run the command to activate virtual environment>env\Scripts\activate

(after successful run, cmd window will look like '(env) C:\faceRecog>' means you have successfully created and activated virtual env and ready to work)




##### Install necessary packages ####################


9) (env) C:\faceRecog>pip install dlib

(somtimes dlib gives error (due to incomaptiability of version/os) saying that "CMake must be installed before....." in that case install dlib by follwing command

 pip install https://pypi.python.org/packages/da/06/bd3e241c4eb0a662914b3b4875fc52dd176a9db0d4a2c915ac2ad8800e9e/dlib-19.7.0-cp36-cp36m-win_amd64.whl#md5=b7330a5b2d46420343fbed5df69e6a3f )

10) (env) C:\faceRecog>pip install face_recognition
11) (env) C:\faceRecog>pip install imutils
12) (env) C:\faceRecog>pip install opencv-python

##########  NOW YOU ARE READY To Test SCRIPT  ##############################

Before testing script there are few points to keep in mind

(a) Application can recognize person only if it can see face of subject. It may fail with side face or partial face.
(b) As we are training model with only one image, make sure atleast this image if of good quality (not too noisy or blured)
(c) Acuracy of recognition can be improved if we train model with more and more images.
(d) Application can also detect multiple faces in a frame, for that please train model with images of your friends and use webcam to recognize them. However, it 
    can also detect face in mobile phone, be sure that you are not getting reflection at mobilephone screen and face shown in mobile screen is large enough to recognize.
    Otherwise system accuracy will decrease with small faces.

==========To test model =====================

To recognize face from image-----------
13) (env) C:\faceRecog>python recognize_faces_image.py --encodings encodings.pickle --image examples/obama.jpg
(NOTE: Make sure the image you want to test is present in 'examples' folder)


To recognize face from webcam-----------
if you want to identify face using webcam then issue following command in cmd window
14)(env) C:\faceRecog>python recognize_faces_video.py --encodings encodings.pickle


if you want to identify face using webcam and save recognized video in harddisk of system then issue following command in cmd,
this will save output video in folder named 'output'.

15) (env) C:\faceRecog>python recognize_faces_video.py --encodings encodings.pickle --output output/recognized_face.avi --display 1





==========To re-train model with own database =====================
16)(env) C:\faceRecog>python encode_faces.py --dataset dataset --encodings encodings.pickle





--------------------------------------------Over-----------------------------------------------------------------
