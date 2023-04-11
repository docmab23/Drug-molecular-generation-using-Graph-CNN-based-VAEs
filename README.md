# Molecular embeddings and De-novo drug generation

## The .ipynb notebook shows 2 things
* Shows how can we make molecular embeddings using different methods
* How can we generate molecules as graphs using Graph-CNN based Variation Autoencoder approach

### Different ways to make a molecular embedding as show in the notebook:
* Vectorize SMILES and train an Autoencoder to get a latent embedding for downstream tasks.
* Using Morgan fingerprints (a type of molecular fingerprints).
* A word2Vec model, treating molecules as sentences, yes you heard that right.


### De-novo Molecular generation
Dataset: `csv_path = keras.utils.get_file(
    "/content/250k_rndm_zinc_drugs_clean_3.csv",
    "https://raw.githubusercontent.com/aspuru-guzik-group/chemical_vae/master/models/zinc_properties/250k_rndm_zinc_drugs_clean_3.csv",
)`








This model is trained to optimize four losses:

Crossentropy
KL divergence loss
Property prediction loss
Graph loss (gradient penalty)
