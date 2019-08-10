# secure-gun

Python Software Module for SecureGun prototype.
<br><br><br>

The 5-layer Convolutional Neural Network, which was trained on the images, contained the
following structure: <br>
• Image Resizing. At the onset, all images are resized to 150 by 150 pixels for the sake<br>
of uniformity in data. This also allows for our image filter (which is pre-determined) to<br>
convolve over images in a standard, non-random manner.<br>
• 3 Convolutional layers. The first 2 layers output feature maps of 32 dimensions. The<br>
third layer outputs a feature map of 64 dimensions.<br>
• 2 Dense layers. After the convolutional layers, our model contains 2 fully connected layers<br>
which further process the feature maps.<br>
• A Flatten function. This intermediate step allows for the 3-dimensional feature maps<br>
outputted by the convolutional layer to be converted into a 1-dimensional feature vector<br>
that is then passed through a dense layer.<br>
• Max Pooling. I implemented Max Pooling in all 3 of the convolutional layers. The<br>
MaxPooling2D Keras function was very handy in its ability to reduce the size of our feature<br>
map without compromising the value of the features.<br>
• Activation functions. With the exception of the final layer, all other layers implement<br>
the standard ReLU activation function. The final layer is mapped to a sigmoid activation<br>
function which outputs the probability of a PERMIT or DENY label.<br>
• Calculating loss. For image classification, I have found it best to use a binary cross entropy<br>
loss (or log loss) function.<br>
The model was trained in 50 epochs (waves) and took 10 hours using the average CPU on my<br>
laptop. The resulting weights that were learned from the model were stored in a .h5 file. This<br>
would allow us to pre-load the weights for our model to use in the future<br>

