# Dicoding-Image-Classification-Submission
Dicoding Rock Paper Scissors Image Classification using CNN

* Dataset is provided by dicoding 
* 2188 samples
* 60:40 train test split

## Library Used
* Tensorflow
* Keras
* matplotlib
* Numpy
* Pandas

## Data set composition                 

|    |   type      |   paper  |   rock   |   scissors |   total   |
|---:|------------:|---------:|---------:|-----------:|----------:|
|  0 |    original |    712.0 |    726.0 |      750.0 |    2188.0 |
|  1 |       train |    427.0 |    435.0 |      450.0 |    1312.0 |
|  2 |         val |    285.0 |    291.0 |      300.0 |     876.0 |


## Step by Step Model Building
### Split Train and Test files 60:40 composition
### Rescaling Image
### Image Augmenting (train set only)
* Rotation
* Horizontal flip
* Vertical Flip
* Zoom range
* Shear
* Fill mode nearest
* Data generating
* resizing image to 128x128
* batch size 64
* class mode categorical
### Build Convnet
* 1 hidden layer (perceptron 512 units)
* output layer 'Softmax'
* model = keras.Sequential([
*     layers.Conv2D(32, (3,3), activation = 'relu', input_shape= (128,128,3)),
*     layers.MaxPooling2D(pool_size=(2, 2)),
*     layers.Conv2D(64,(3,3), activation= 'relu'),
*     layers.MaxPooling2D(pool_size=(2, 2)),
*     layers.Conv2D(128,(3,3), activation= 'relu'),
*     layers.MaxPooling2D(pool_size=(2, 2)),
*     layers.Flatten(),
*     layers.Dropout(0.5),
*     layers.Dense(512, activation= 'relu'),
*     layers.Dense(3, activation= 'softmax')
*     ])
### Adding Loss Function and Optimizer
* loss : categorical cross entropy
* optimizer adam
* metrics accuracy
### Adding Early stop function using EarlyStopping from tensorflow keras callback
* Minimum change : 0.01
* Number of epoch before stop : 5
### Training the model
* epoch : 30
* steps per epoch : 15
* verbose : 1
* validation steps : 3
* callbacks
 
## Results
* Best Validation Loss: 0.05
* Best Validation Accuracy: 0.98

* Loss

![](/img/download.png)

* Accuracy

![](/img/download%20(1).png)
