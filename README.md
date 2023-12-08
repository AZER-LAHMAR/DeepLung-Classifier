

## Introduction 📜

This project belongs to the Advanced IA Module.</br></br>

It consists of building a deep learning model for classifying lung images into three categories (COVID, NORMAL, PNEUMONIA) using a Convolutional neural network (CNN).</br>
</br>
We will have a graphical interface from which we can test different images to determine the system's relevance.

## Authors ©️
.</br>
<ul>
  <li>Abdennour Samaali
</li>.</br>
    <li>Azer Lahmar</li>
  .</br>
      <li>Mohamed Amine Kaabi</li>.</br>
      <li>Yassine Layouni</li>.</br>
</ul>

## Inputs 📥
<a name="inputs"></a>
The dataset consists of 5228 lung images in PNG format with a size of 256x256 pixels, divided into three categories:
* COVID: 1626 images
* NORMAL: 1802 images
* PNEUMONIA: 1800 images
</br>



## Libraries  💡
<a name="libraries "></a>

📌Numpy

* We used Numpy for manupliting the dimensions of the image
For more you can read the official documentation on the [Numpy](https://numpy.org/doc/stable/). 

📌Matplotlib

* We used Matplotlib for displaying the training history of the model and displaying the image itself.

For more you can read the official documentation on the [Matplotlib](https://matplotlib.org/stable/index.html)

📌Splitfolders

* We used Splitfolders to  divide the dataset randomly into  randomly into 3 datasets: 

📁training 

📁Validation

📁testing  

For more you can read the official documentation on the [Splitfolders](https://pypi.org/project/split-folders/)

📌Tensorflow (Keras)

* We have utilized Keras multiple times throughout this project for various purposes.

For more you can read the official documentation on the [Keras](https://www.tensorflow.org/guide/keras)

## Data prepartion 💡
<a name="data-prepartion"></a>
```
#Split Dataset into 3 folders (train, test and validation)
splitfolders.ratio('./3IDL_DataSet/', output="Output_DataSet", seed=1337, ratio=(0.6,0.2,0.2))
# Set the path to your dataset directory
path_dataset = './Output_DataSet'
```



Define parameters

```
img_dim =256
batch_size = 32

```


Data augmentation and training prepartion

```
train_data = ImageDataGenerator(
    rescale=1./255,
    shear_range=0.2,
    zoom_range=0.2,
    horizontal_flip=True
)

train = train_data.flow_from_directory(
    os.path.join(path_dataset, 'train'),
    target_size=(img_dim, img_dim),
    batch_size=batch_size,
    class_mode='categorical'
)

```



 Data rescaling
```
test_data = ImageDataGenerator(rescale=1./255)

```

Validation data prepartion
```
validation = test_data.flow_from_directory(
    os.path.join(path_dataset, 'val'),
    target_size=(img_dim, img_dim),
    batch_size=batch_size,
    class_mode='categorical'
```

## Building the Model 💡
<a name="building-the-model"></a>

In order to ensure that the Laravel community is welcoming to all, please review and abide by Laravel's [Code of Conduct](https://laravel.com/docs/contributions#code-of-conduct).

## Training the Model 💡
<a name="training-the-model"></a>

Please review [our security policy](https://github.com/livewire/livewire/security/policy) on how to report security vulnerabilities.

## Testing the Model 💡
<a name="testing-the-model"></a>

Livewire is open-sourced software licensed under the [MIT license](LICENSE.md).

## Model evaluation 💡
<a name="model-evaluation"> </a>

Yassine

