# Fruit-and-vegetables-classification
Image classification using ResNet50 model and Flask web application. 2D TSNE visualization.

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
  <summary><em>Data augmentation</em></summary>
  I'm using tf.keras.preprocessing.image.ImageDataGenerator to make augmentation of images(spect ratio resizing, shifting, blurring, flipping)
</details>
<details>
  <summary><em>Training a model</em></summary>
  I'm using tf.keras.applications.resnet50.ResNet50 with input shape of the image (224, 224, 3). Weights from imagenet dataset and max pooling in layers.
  Before fine-tuning accuracy was 0.90023.
  </details>
<details>
  <summary><em>Fine-tuning model</em></summary>
  As a fine-tuning I add this layers:<br>
  <img src="https://user-images.githubusercontent.com/58363847/167637983-ca68e0e2-9837-4196-8a6d-533e91e059c7.png"/><br>
  And the last five layers of the base model were also unfrozen and trained.
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
  You can find video of testing my web application <a href="https://youtu.be/43Vexiiac5k">here</a>. You can use my weights, which you can find in directory saved_model or you can train your model and save weights by running file <a href="https://github.com/EvelinaAlexiutenko/Fruit-and-vegetables-classification/blob/main/Fruits_and_vegetables.ipynb">Fruit-and-vegetables-classification</a><br> 
  </details>
<details>
