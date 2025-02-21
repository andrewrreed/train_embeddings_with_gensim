# Learning item embeddings with Gensim's Word2Vec
[Gensim](https://radimrehurek.com/gensim/index.html) is one of the fastest libraries for training vector embeddings and provides the most well-known and oft-used implementation of the Word2Vec algorithm. While word embeddings are the most common, they're certainly not the only use case! Vector embeddings can be learned for just about anything: hotel listings, user profiles, products on an e-commerce website, and more. These embeddings can then serve as features for downstream tasks like classification, clustering, or in recommendation systems. 

![](images/gensim.png)

The notebook in this repo demonstrates how to train Gensim's Word2Vec algorithm on non-traditional (e.g. not human language) data while identifying some conceptual and technical challenges, including: 
* how to structure non-language data for Word2Vec consumption
* hyperparameter tuning with the Ray Tune library
* how to use callbacks for early stopping (thus speeding up hyperparameter optimization)

We also demonstrate two simple methods for evaluating the learned embeddings
* qualitative comparison of similar embeddings
* quantitative analysis of their performance in a simple recommendation system

### Installation
Package installation occurs in the first cell of the Jupyter Notebook, which accesses the `requirements.txt` file in the top-level directory. 

In CML/CDSW, simply start a new Jupyter Notebook session with 2CPUv/4GiB [TODO: check this] and proceed! 

### Data 
We make use of the Online Retail dataset, which consists of customer purchase orders through an e-commerce boutique over the course of a year. The data is open source with citation to the original authors. We obtained the data from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/online+retail). 

Daqing Chen, Sai Liang Sain, and Kun Guo, Data mining for the online retail industry: A case study of RFM model-based customer segmentation using data mining, Journal of Database Marketing and Customer Strategy Management, Vol. 19, No. 3, pp. 197â€“208, 2012 (Published online before print: 27 August 2012. doi: 10.1057/dbm.2012.17).

### Related Work
Some of the code in the Jupyter Notebook was originally developed for the Cloudera Fast Forward Labs report on [Session-based Recommendation Systems](https://session-based-recommenders.fastforwardlabs.com/). The original repo can be found [here](https://github.com/fastforwardlabs/session_based_recommenders) and includes scripts that can be automated to perform the tasks we demonstrate in this notebook. 

Cloudera Fast Forward also published a [blog post](https://blog.fastforwardlabs.com/2021/09/20/how-and-when-to-enable-early-stopping-for-gensims-word2vec.html) that explores the _why_ behind the early stopping mechanism used in this repo.


## Deploying on Cloudera Machine Learning (CML)
There are three ways to launch this notebook on CML:

* **From Prototype Catalog** - Navigate to the Prototype Catalog in a CML workspace, select the "Item Embeddings with Gensim Word2Vec" tile, click "Launch as Project", click "Configure Project"
* **As ML Prototype** - In a CML workspace, click "New Project", add a Project Name, select "ML Prototype" as the Initial Setup option, copy in the [repo URL](https://github.com/fastforwardlabs/item-embeddings-with-gensim-word2vec), click "Create Project", click "Configure Project"
* **Manual Setup** - In a CML workspace, click "New Project", add a Project Name, select "Git" as the Initial Setup option, copy in the [repo URL](https://github.com/fastforwardlabs/item-embeddings-with-gensim-word2vec), click "Create Project".

Once the project has been initialized in a CML workspace, run the notebook by starting a Python 3 Jupyter notebook server session. All library and model dependencies are installed inline in the notebook.

