# Face Recognition
這是我用自己朋友圈的照片來訓練的人臉辨識練習，總共有7人，每人15張當train data，5張當test data。
當今頂尖的人臉辨識都在loss function下了許多功夫，例如FaceNet只要128維的descriptor，就能用它的triplet loss train出很強的結果。不過我這邊先用簡單的svm來做，所以採用高維的vgg face descriptor來用，有4096維。
training的cross validation平均可以超過90%，testing也能超過90%。
而且這7人裡面有一對非常像的雙胞胎，拿來做實驗非常好玩。

由於朋友的照片不好公開，所以目前只放code上來

## Prerequisite
matplotlib, opencv, dlib, numpy, sklearn, imutils等套件

## pre-trained models
face detector: 使用opencv的res10 ssd caffe model，檔名叫做"res10_300x300_ssd_iter_140000.caffemodel"，網路上很容易找到
landmark detector: 使用dlib的shape detector來偵測68個人臉特徵點，檔名為"shape_predictor_68_face_landmarks.dat"，一樣很容易下載
face descriptor: 使用vgg face的network，可以從他們的官網下載http://www.robots.ox.ac.uk/~vgg/software/vgg_face/

##	extract_embeddings2
擷取vgg face特徵向量，存成csv檔

##	train_faces
用svm做training, 把train好的svm存成檔案(pickle.dump)

##	test_daces
測試test data的正確率

##	testing_single, testing_multi
跑一些其他的照片


## References

 1. [OpenCV Face Recognition](https://www.pyimagesearch.com/2018/09/24/opencv-face-recognition/) 
 2. [Face detection with OpenCV and deep learning](https://www.pyimagesearch.com/2018/02/26/face-detection-with-opencv-and-deep-learning/)
 3. [Facial landmarks with dlib, OpenCV, and Python](https://www.pyimagesearch.com/2017/04/03/facial-landmarks-dlib-opencv-python/)
 4. [Face Alignment with OpenCV and Python](https://www.pyimagesearch.com/2017/05/22/face-alignment-with-opencv-and-python/)

