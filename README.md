# secure-gun

Python Software Module for SecureGun prototype.


The 5-layer Convolutional Neural Network, which was trained on the images, contained the
following structure:
• Image Resizing. At the onset, all images are resized to 150 by 150 pixels for the sake
of uniformity in data. This also allows for our image filter (which is pre-determined) to
convolve over images in a standard, non-random manner.
• 3 Convolutional layers. The first 2 layers output feature maps of 32 dimensions. The
third layer outputs a feature map of 64 dimensions.
• 2 Dense layers. After the convolutional layers, our model contains 2 fully connected layers
which further process the feature maps.
• A Flatten function. This intermediate step allows for the 3-dimensional feature maps
outputted by the convolutional layer to be converted into a 1-dimensional feature vector
that is then passed through a dense layer.
• Max Pooling. I implemented Max Pooling in all 3 of the convolutional layers. The
MaxPooling2D Keras function was very handy in its ability to reduce the size of our feature
map without compromising the value of the features.
• Activation functions. With the exception of the final layer, all other layers implement
the standard ReLU activation function. The final layer is mapped to a sigmoid activation
function which outputs the probability of a PERMIT or DENY label.
• Calculating loss. For image classification, I have found it best to use a binary cross entropy
loss (or log loss) function.
The model was trained in 50 epochs (waves) and took 10 hours using the average CPU on my
laptop. The resulting weights that were learned from the model were stored in a .h5 file. This
would allow us to pre-load the weights for our model to use in the future


If all US rifle owners were morally sound and responsible to an incredibly high standard, mass
shootings would be a phenomenon of the past. Given the unlikelihood of this, I present a Deep
Learning framework that entails mimicking the complex decision making process of a responsible
rifle owner in a software module. This software module works in conjunction with a camera, GPS
module, and stepper motor, allowing for the creation of a new concept. Despite this project’s
status as a prototype, much thought was given to each design feature. Supplementary files
are included in the zip file including the code which is provided as Jupyter Notebook (.ipynb)
files. 
As an individual who’s spent time trying to empathize with the victims, I began realizing
how grave this problem was becoming. I wanted, desperately, to create some device that would
somehow protect 2nd Amendment rights and prevent mass shootings.
Admittedly, this project, while legitimate and sound in the technical realm, is incapable of realworld implementation simply because government intervention is required. However, I’m content
(at least to some degree) that I have devised a technical solution which has the potential to start
a new conversation and perhaps encourage others to build off my work. This is my only goal,
now and in the future, as an entrepreneur.
