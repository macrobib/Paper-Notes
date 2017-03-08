### Batch Normalization:
In a deep neural network the distribution of each layers input changes during training as a result of change in the distribution of the previous layers.  
This results in difficulty in training the network as the learning rate and careful paremeter optimization are called for.  
- Batch normalization involves making normalization a part of the mini batch, a part of the training.
- Allow use of much higher learning rate and less careful variable initializations.
- Change in the input distribution also called covariate shift is handled via domain adaptation.
- In a system consisting of arbitrary transformations, its an advantage to have same distribution among training and test data.
- Till recently whitening has been considered as one way to improve the training convergence of a network, i.e to convert data set to have zero mean and unit variance.
- Doing normalization outside of training mostly results in the model failure.
- By representing the activation normalization using parameters gamma and beta. Normalized values are scaled and shifted.
- In batch setting where each training set is based on the entire training set, we would use the whole set to normalize activation. However, this is impractical when using stochastic optimization.
- These parameters are learning along with the network and restore the represntative power of the network.
- Each mini batch produces estimates of mean and variance. This way statistics used for normalization can fully participate in gradient descent.
- The key idea here is that Batch normalization does not independently process the activation in each training example. Rather BN depends on the training example and other examples in the mini-batch.
- Thus, BN transform is a differentiable transformation that
introduces normalized activations into the network. This ensures that as the model is training, layers can continue learning on input distributions that exhibit less internal covariate shift, thus accelerating the training.
- So after training the gamma and beta are replaced with value augmented by mean and variance.
- Batch normalization is applied just before the non linearity is applied.
- In traditional deep networks, too-high learning rate may result in the gradients that explode or vanish, as well as getting stuck in poor local minima. Batch Normalization helps address these issues. By normalizing activations throughout the network, it prevents small changes to the parameters from amplifying into larger and suboptimal changes in activations in gradients; for instance, it prevents the training from getting stuck in the saturated regimes of nonlinearities.
- Batch normalization prevents scale of the layers from amplifying the gradients during training. i.e. the scale does not affect the jacobian. Moreover larger weights will lead to smaller gradients and batch normalization will stabilize the parameter growth.
- Batch normalization will lead to layer jacobians having values closer to 1.
- Batch normalization regularises the network resulting in less dependency on the droput.
- Similarly there is no need for local response normalization.
- Thorough shuffling.
- Reduce photometric distortion, thus the trainer focus more on real images than distorted images.
- Ensemble network: An ensemble of network were created by following:
	- Drouput with 5-10% rate.
    - Non-convolution per activation batch normalization with last hidden layer.