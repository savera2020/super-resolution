# Deep Network cascade for image super-resolution
The project is to implement the deep autoencoder cascade for image super-resolution.Here we gradually upscale low-resolution images layer by layer.
# Non-Local Self Similarity Search 
The first step in this method involves enhancing the input the high-frequency texture details through a Non-Local Self Similarity (NLSS) search on the input image.
# AutoEncoder
The next step is to take NLSS results as the input to a standard auto encoder to suppress the noises and collaborate the overlapping reconstructed patches.
Here to reduce the learnable parameters and make auto-encoder easily controllable, we used weight-tying on all the patches and L1 sparse constraint on hidden neurons.
# Stacked AutoEncoder
Closing the loop on the 2 steps forms a cascade layer, named Stacked AutoEncoder which refines the super-resolution image well.Multiple SA models can be successively concatenated into deep network cascade.
The higher layer of this Deep network takes the output SR image of the lower layer as input.The Magnification factor of the learned SR image can be enlarged by increasing the network layers.


