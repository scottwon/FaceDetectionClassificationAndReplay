# Facial Detection, Classification and Replay
This is the course project for 'Programming Practices'.

This work has been included by a MOOC project of my university: https://www.icourse163.org/course/BUPT-1003561002. The case 20 in lesson 10, unit 4 demonstrates some features of my work.

My work consists of several components: facial detection, facial classification, the replay of the key frame and the recognition of the emotion.

This was the first time I encountered a computer vision problem and I learned a lot.

I learned that the Haar-like features describe the local features of the object and the adaboost algorithm can exploit the local features and make a global decision, which is the basis of object detection.

I learned that before the convolutional neural network grew to prominence, several approaches had been proposed to solve the problem of image classification. I tried both CNN and non-CNN methods. For non-CNN methods, I tried PCA, LDA and LBPH methods. For CNN methods, I tried to finetune the network of VGG-16.

Besides OpenCV, there are several powerful toolkits that facilitate the processing of facial images. DLib can track the 68 landmarks of the faces and I use the locations of the facial landmarks and SVM to predict the emotion of people.

Many face detection algorithms are not rotation-invariant, that is, their performance will drop dramatically if the facial images are rotated. To address the issue of rotated face detection, I tried to combine the optical flow method with the face detection algorithms. Once the face is detected, the key points in the facial area are detected simutaneously. I use optical flow to keep tracking the key points in the facial area so that even if the face detection algorithms fail to recognize the face in adverse cases, the optical flow will still confirm the existence of the face.

Once a new face appears in the videostream, the program will record the frame in the .vdm file. When we load the .vdm file, the program will parse the file and replay all the key frames in which new faces appear.
