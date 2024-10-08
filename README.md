# Molecular embeddings and De-novo drug generation

## The .ipynb notebook focuses on:
* How can we make molecular embeddings using different methods ? 
* How can we generate molecules as graphs using Graph-CNN based Variation Autoencoder approach ?

### Different ways to make a molecular embedding as show in the notebook:
* Vectorize SMILES and train an Autoencoder to get a latent embedding for downstream tasks.
* Using Morgan fingerprints (a type of molecular fingerprints).
* A word2Vec model, treating molecules as sentences, yes you heard that right.


### De-novo Molecular generation

Dataset: `csv_path = keras.utils.get_file(
    "/content/250k_rndm_zinc_drugs_clean_3.csv",
    "https://raw.githubusercontent.com/aspuru-guzik-group/chemical_vae/master/models/zinc_properties/250k_rndm_zinc_drugs_clean_3.csv",
)`

### A step-by-step overview:
* Make graphs from SMILES
* Make Adjacency and feature tensors from Graphs 
* Make Graph convolution layes
* Make a Variational Encoder-decoder architecture from those layers to learn the distribution (mu and sigma vectors)
* Train the model and get novel molecules out of the latent embedding 

![image](https://user-images.githubusercontent.com/31487695/231053220-d3491cda-f340-4119-ad42-c21ff1e0a584.png)

#### This model is trained to optimize four losses:

* Crossentropy
* KL divergence loss
* Property prediction loss (QED scores)
* Graph loss (gradient penalty)


![image](https://user-images.githubusercontent.com/31487695/231052857-8de54064-7128-4eaa-b693-0c7c171fd41a.png)
