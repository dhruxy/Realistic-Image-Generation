# Generative-Adversarial-Networks

Implemented and trained various Generative Adversarial Networks (GANs) to generate images using the CIFAR10 dataset. The GAN architectures implemented are -
1. Vanilla GAN
2. DCGAN ( Deep Convolutional GAN)
3. WGAN-GP ( Wasserstein GAN with gradient penalty )
4. C-GAN ( Conditional GAN )

# Brief Model Description 
**General Adversarial Networks** are used in image generation. The basic concept of GANs is that it has 2 networks playing an adversarial game against each other ( where loss of one player is gain of the other). One of them is called Generator which generates images from random noise and the other is called Discriminator which distinguishes between fake and real images. The objective of the generator is to generate images that are indistinguishable from the real images, so that the discriminator can not decide which image is real and will have to guess with a probability of 0.5. By competing against each other both the networks train to get better and better.

<p align="center">
 <img  width="452" height="500" src="Resources\GAN architecture.png">
</p>

1. **Vanilla GAN**
This model is the most basic implementation, just to get a grasp of the working of generative adversarial networks. Both the generator and the discriminator are using simple neural networks with very few layers . BCEloss function is used to compute the loss and Adam optimizer (with default parameters) is used to optimize both the networks .

2. **DCGAN**
Deep Convolutional GAN is a better implementation which uses a deeper convolutional neural network for both discriminator and optimizer.

3. **WGAN-GP**
Wasserstein GAN with gradient penalty is an improvement of DCGAN and tries to make the training process more stable. Instead of the earlier used KL divergence and JS divergence it uses Wasserstein distance to minimize the difference between the probability distribution of the real image and the generated images as to generate real looking images. 

4. **C-GAN**
Conditional GAN is an improvement in the WGAN-GP model , where the classification labels of the image set can help improve the training process. Here we add an embedding layer in our image channels which supplies our generator information about which class to generate and the critic also judges fake and real images for the same label class. Thus the corresponding real and fake images (in the image grid)  for a particular step are of the same class. 

*For more details on the architecture and loss functions please refer to the project report.*

# Results and Comparison

<table>
<tr>
	<th>GAN</th>
    <th>Vanilla GAN</th>
    <th>DCGAN</th>
</tr>
<tr>
    <th>Generated Images</th>
    <td><img src="Resources\Vainlla_GAN.png" width="300" /></td>
    <td><img src="Resources\DC_GAN.png" width="300" /></td>
</tr>
<tr>
	<th>GAN</th>
    <th>WGAN-GP</th>
    <th>C-GAN</th>
</tr>
<tr>
    <th>Generated Images</th>
    <td><img src="Resources\WGAN-GP.png" width="300" /></td>
    <td><img src="Resources\CGAN.png" width="300" /></td>
</tr>
</table>

*For more detailed comparison please refer to the project report.*

# Conclusion

I have used 4 different architectures for this project and with each model I have tried to improve the fake image and make it indistinguishable from the real image. Due to the resources available I was only able to train these models for around 50 epochs and I believe that if these models are further trained they should be able to generate even better results. For training of GANs it is highly necessary to select the correct hyperparameters and when doing in real practice a loop for great hyperparameter search would be really helpful as with correct hyperparameters the model will converge really fast and produce great fake images.













