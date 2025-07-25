High dimensional data can be well approximated by low-dimensional manifolds (manifold hypothesis) and neural networks trained on such data will have features that depend on the intrinsic dimensionality; quantifying this latent dimensionality can help understanding.

Currently, there exists no universal approach to quantify the dimensionality of the input space. We investigated if we can find a useful definition of dimensionality while working with dimensionality reduction techniques (DRTs) applied in classification tasks. To explore this, we assessed the behaviour of two DRTs across changing latent dimensionality.

We employed PCA and VAE in parallel on MNIST and CIFAR-10 datasets, generating dimensionality-reduced image datasets, using latent spaces ranging from very low-dimensional (10 PCs for PCA; 10 bottleneck units for VAE) to approaching the original input dimensionality (up to 500; for reference, original space for MNIST is 784). We measured the classification accuracy of these dimensionality-reduced images using a classifier trained with the original images.

For PCA, as the latent space dimensionality increases, the image reconstruction error gets smaller, and the classification accuracy increases, plateauing around 80 dimensions.

In contrast, with the VAE classification accuracy and reconstruction error reach a plateau earlier, at around 50 dimensions. At dimensions higher than 100, these metrics deteriorate. We verified that these results are not due to overfitting, and persist even on modifying the Gaussian regularization of the VAE (beta VAE).

Our initial results indicate that VAE’s reconstructions reach higher classification accuracy at a lower latent dimensionality compared to PCA. This suggests that VAEs are better suited to be used for measuring the dimensionality of the input space, provided that regularization is appropriate.
Our follow-up experiments are oriented towards understanding this behaviour and defining the manifold dimensionality.

<img width="635" height="444" alt="image" src="https://github.com/user-attachments/assets/3f34da89-f4a0-4bbc-a276-289a56c974b3" />


<img width="1267" height="1008" alt="image" src="https://github.com/user-attachments/assets/66f0613b-181a-4a9c-9311-95bd6f684acb" />
