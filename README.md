# Fruit-and-vegetables-classification
Image classification using ResNet50 model and Flask web application.

<img src="https://user-images.githubusercontent.com/58363847/167606900-62e6e89d-7261-4ac3-be00-f98c38ea947f.png" width="450" height="300" />
<img src="https://user-images.githubusercontent.com/58363847/167606928-f4433c1b-e08b-45c4-aedd-921be332a43b.png" width="450" height="300" /><br>
To see the video about testing web-app click here:
<a href="https://youtu.be/43Vexiiac5k">ResNet-50 web-app for image classification</a><br>
The dataset you can find <a href="https://www.kaggle.com/datasets/kritikseth/fruit-and-vegetable-image-recognition">here</a>.
<br>

## Requirements:
cuda_11.2 <br>
python version- 3.6.2
<br>
## Algorithm:
<details>
  <summary><em>Data preparation</em></summary>
  You can make your custom dataset with the structure - one subdirectory for each person: <br>
  <img src="https://user-images.githubusercontent.com/58363847/167355965-eb791e52-a8d9-4381-8c63-719b12fbe5bd.jpg" wight = 400 height =400/><br>
  By working with this project FaceNet badly recognized people on selfies that's why I need to do augmentation. The augmentation function resizes the original photo
  and overlays it on a bigger background.
</details>
<details>
  <summary><em>Detection of the face with MTCNN</em></summary>
  I am using this network to extract face from the photo. If MTCNN does not find a face, please go back to the previous step of the algorithm and do augmentation.
  Example of MTCNN application:
  <p float="left">
  <img src="https://user-images.githubusercontent.com/58363847/167314019-abf4ee59-ce82-4870-8308-1c6f80e73938.jpg"/>
  </p>
  MTCNN also find a person in a sunglasses:<br>
  <img src="https://user-images.githubusercontent.com/58363847/167359791-1d6622c7-19df-4426-b56f-ff5bcf2f2987.png"/><br>
  </details>
<details>
  <summary><em>Creating an embedings with FaceNet</em></summary>
  I use pretrained FaceNet because of the fact that recognition NN need to be train on a large dataset. You can find and download model
  <a href="https://github.com/nyoki-mtl/keras-facenet">here</a>. We need embedings to perform vector classification. The FaceNet model can be used as part of the
  classifier itself, or we can use the FaceNet model to pre-process a face to create a face embedding that can be stored and used as input to our classifier model.
  This latter approach is preferred as the FaceNet model is both large and slow to create a face embedding.
  </details>
  <details>
  <summary><em>2D visualization using TSNE</em></summary>
  I use TSNE to depict the distribution of classes.
  <br>
  Result:
  <br>
  <img src="https://user-images.githubusercontent.com/58363847/167635987-450c81f2-b73f-45e1-9191-aedb13af4896.jpg" wight = 300 height =300/><br>
  </details>
  <details>
  <summary><em>Web application using Flask</em></summary>
  You can find video of testing my real-time webcam demo in the link above. Also by running file FaceDetector.py you can test it by yourself. But before it you need to   built training dataset and make embedins be running FaceTrainder.py. For faster recognition you need to use CUDA. 
  </details>
<details>
  <summary><em>References</em></summary>
  
  1. https://arxiv.org/pdf/1503.03832.pdf - FaceNet;
  
  2. https://medium.com/analytics-vidhya/introduction-to-facenet-a-unified-embedding-for-face-recognition-and-clustering-dbdac8e6f02 - Good FaceNet explanation;
  
  3. https://medium.com/@iselagradilla94/multi-task-cascaded-convolutional-networks-mtcnn-for-face-detection-and-facial-landmark-alignment-7c21e8007923 - MTCNN;
  
  4. https://machinelearningmastery.com/how-to-develop-a-face-recognition-system-using-facenet-in-keras-and-an-svm-classifier/;
  
  5. https://github.com/davidsandberg/facenet -FaceNet original repo;
  
  6. Basic theory from Deeplearning.ai:
    https://www.youtube.com/watch?v=-FfMVnwXrZ0&list=PLkDaE6sCZn6Gl29AoE31iwdVwSG-KnDzF&index=33&ab_channel=DeepLearningAI
    https://www.youtube.com/watch?v=96b_weTZb2w&list=PLkDaE6sCZn6Gl29AoE31iwdVwSG-KnDzF&index=34&ab_channel=DeepLearningAI
    https://www.youtube.com/watch?v=6jfw8MuKwpI&list=PLkDaE6sCZn6Gl29AoE31iwdVwSG-KnDzF&index=35&ab_channel=DeepLearningAI
    https://www.youtube.com/watch?v=d2XB5-tuCWU&list=PLkDaE6sCZn6Gl29AoE31iwdVwSG-KnDzF&index=36&ab_channel=DeepLearningAI
    https://www.youtube.com/watch?v=0NSLgoEtdnw&list=PLkDaE6sCZn6Gl29AoE31iwdVwSG-KnDzF&index=37&ab_channel=DeepLearningAI
 
  7. https://www.youtube.com/watch?v=yfDjsuxIKA4&t=2718s - Training other models using Tensorflow Object Detection;
  
  8. https://www.youtube.com/watch?v=LUO385H9A4c&t=2306s&ab_channel=NTA.DataScience%D0%B8AI%D0%B2%D0%B0%D1%83%D0%B4%D0%B8%D1%82%D0%B5 - Face Recognition with FaceNET;
  
  9. https://youtu.be/cyRHeNQL0-4 - Top 6 NN for solving face recognition problem;
  
  10. https://github.com/ram-ch/RealTimeFaceRecognition - Good another github repo of solving this problem;
  
  11. https://youtu.be/lwcLwhXbi1M - Good video about solving this problem;
  
  12. https://towardsdatascience.com/face-detection-using-mtcnn-a-guide-for-face-extraction-with-a-focus-on-speed-c6d59f82d49 - faster MTCNN ;
  </ul>
</details>
<br>

