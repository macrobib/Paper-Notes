### End to end driving for self driving.

- Convolutional neural network is trained on raw pixels from a single front facing camera directly to steering commands.
- The system automatically learns internal representations of the necessary processing steps such as detecting useful road features with only human steering angle as the training signal.
-The system consists of 3 sets of images from left, center and right camera.
- To let the car learn to recover from the mistake, training data is augmeted with additional images that shows car in different shifts from the center of the lane and rotations from the direction of the road.
- Images for two specific off-center shift can be obtained from the left and right camera.
- The data is collected over multiple locations and under diverse conditions.
- In total 72 hours of data is collected.
- The collected data is augmented with additional perturbation to enable the network to learn to recover from a error condition.
- In the testing phase of the network only a single front camera is fed to the network.
- The network is pre validated on a simulator and then tested on actual road conditions.
- The network consists of 5 convolutional layers and 3 fully connected layers.

| Layer  		  | Input  | Weight  | Output  | Feature count  |
|---	 		  |---	   |---	     |---	   |---			    |
|  Normalization | 3 x 66 x200  | -   | 3x66x200  |   |
|  Convolution  | 3 x 66 x 200| 5x5x3x24 | 24x31x98 |   |
|  Convolution |  24 x 31 x 98 | 5x5x24x36  | 36x14x47  |   |
|  Convolution |  36 x 14 x 47| 5x5x36x48  | 48x5x22  |   |
|  Convolution |  48 x 5 x 22| 3x3x48x64  |  64x3x20 |   |
|  Convolution |  64 x 3 x 20| 3x3x64x64  |  64x1x18 |   |
|  Fully connected |  1164 |   |  100 |   |
|  Fully connected |  100 |   |  50 |   |
|  Fully connected |  50 |   |  10 |   |

- Visualizing the representation used by different layers.
- Implementation in Torch with ports in tensorflow.
- TODO: Visualizing the layer pattern.