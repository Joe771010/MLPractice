# Face Recognition
我的人臉辨識可以分成以下幾個步驟
(1) Face detection
(2) Face landmark detection >> alignment
(3) Face embedding 
(4) Training 
(5) Evaluation

## Face Detection
OpenCV與dlib都有提供傳統的人臉偵測方法，分別是用Haar cascades與HOG來做。

我們也可以使用deep learning來跑人臉偵測，網路上有非常多訓練好的model，用OpenCV的dnn module讀進來就可以用了。Adrian的blog裡面提供了 "res10_300x300_ssd_iter_140000.caffemodel" 這個 model，我覺得效果比傳統的方法穩定一些，但是如果人臉太小還是會抓不到。

為了讓這個face detector能夠抓到所有training data的人臉，我都有先處理過照片，讓人臉相對於整張照片的面積不要太小，以下圖為例。
![人臉太小，抓不到](https://github.com/Joe771010/MLPractice/blob/master/face_recognition/doc/no_detect.jpg =100x)
![人臉大小OK](https://github.com/Joe771010/MLPractice/blob/master/face_recognition/doc/yes_detect.jpg =100x)

## References

 1. [OpenCV Face Recognition](https://www.pyimagesearch.com/2018/09/24/opencv-face-recognition/) 
 2. [Face detection with OpenCV and deep learning](https://www.pyimagesearch.com/2018/02/26/face-detection-with-opencv-and-deep-learning/)
 3. [Facial landmarks with dlib, OpenCV, and Python](https://www.pyimagesearch.com/2017/04/03/facial-landmarks-dlib-opencv-python/)
 4. [Face Alignment with OpenCV and Python](https://www.pyimagesearch.com/2017/05/22/face-alignment-with-opencv-and-python/)

