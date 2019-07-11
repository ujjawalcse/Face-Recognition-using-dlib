# Face-Recognition-using-dlib

Step 1 : Install dlib library
  -> pip install dlib ( it requires visual studio c++ build tools be installed as prerequisite )

Step 2 : Install face_recognition library
  -> pip install face_recognition (dlib should be installed )

Step 3: Install libraries for better video and image processing
  -> pip install imutils
  -> pip install opencv-python
  
DATASETS : 
  My dataset contains three folders namely, 
    1. salman (This folder contain 100 salman khan's images)
    2. shahrukh (This folder contain 100 shahrukh khan's images)
    3. unknown ( This folder contain 100 images not belonging to above two folders i.e images of random people)
   
   You can keep as  many folder as you want and perform face recognition. Just keep images in separate folder
   belonging to each people. 
   
FOR VIDEO :
   you can download any video belonging to those person and can perform face recognition.
   I have uploaded my input video here in video directory.
   You have to change the video path to your input video on which you want to perform face recognition in line 28 in
   recognize_faces_video.py 
   
 STEPS TO RUN FACE RECOGNITION :
  step 1: run encode_faces.py that will encode every faces from image dataset as 128 dimensional vector and save it as .pickle file.
    -> python encode_faces.py --dataset image_datasets --encodings encodings1.pickle/
       detection-method hog
     NOTE:- ->image_datasets is my folder name where salman,shahrukh and unknown folders are stored
            ->encodings1.pickle is stored at the your cwd. you can give any name just extension should be .pickle (here name is encodins1)
            ->you can use either hog or cnn as detection method. hog is faster but less accurate as compared to cnn.But cnn requires
              powerful machine as it contains complex computation.
    
   step 2: After running encode_faces.py, you will have encodings1.pickle file.
           Now run recognise_faces_video.py as:
        -> python recognise_faces_video.py --encodings encoding1.pickle --output output/vid1.avi --display 1 /
            detection-method hog
           NOTE:- ->it requires first argument as .pickle file that we have created in first step.
                  ->second argument --output is the path to output directory where you want to save your output video after 
                    face recognition.
                  ->Third argument is to diplay your frames on screeen. if it is 1 then display on screen otherwise don't display.
                  -> Fourth argument is same as in first step detection-method.
                  
     That's it. Now you can check your output video which will contain bounding boxes on each faces recognized.
                  
