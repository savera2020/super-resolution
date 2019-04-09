# Deep Network cascade for image super-resolution
* The project is to implement the deep autoencoder cascade for image super-resolution.
* Here we gradually upscale low-resolution images layer by layer.
# Non-Local Self Similarity Search 
* The first step in this method involves enhancing the high-frequency texture details of input image through a Non-local Self Similarity (NLSS) search.
![NLSS_results](https://github.com/savera2020/super-resolution/blob/master/result/NLSS_result.png)
# AutoEncoder
* The next step is to take NLSS results as the input to a standard auto encoder to suppress the noises and collaborate the overlapping reconstructed patches.
* Here to reduce the learnable parameters and make auto-encoder easily controllable, we used weight-tying on all the patches and L1 sparse constraint on hidden neurons.
![AutoEncoder_results](https://github.com/savera2020/super-resolution/blob/master/result/AUTOENCODER_RESULT.png)
# Stacked AutoEncoder
* Closing the loop on the 2 steps, forms a cascade layer named Stacked AutoEncoder, which refines the super-resolution image well.Multiple SA models can be successively concatenated into deep network cascade.
* The higher layer of this Deep network takes the output SR image of the lower layer as input.The Magnification factor of the learned SR image can be enlarged by increasing the network layers.
![SA_results](https://github.com/savera2020/super-resolution/blob/master/result/result2_56_56.png)
* To reduce the errors that propagate through network layers we use the back-propagation technique to constrain the super-resolved image in each layer.
# Results 
* After tarining the DNC model over a training data consisting of 1 million images patches using greedy layer-wise optimization startegy we obtained appreciable results as shown below. 
> ![input_image](https://github.com/savera2020/super-resolution/blob/master/result/input.png)
![output_image](https://github.com/savera2020/super-resolution/blob/master/result/resolution_results_56_56.png)

