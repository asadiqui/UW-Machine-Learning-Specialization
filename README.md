# Table of Contents
1. [Overview](#overview)
2. [Getting Started on a python environment](#getting-started-on-a-python-environment)
	1. [Notes](#notes)
3. [Learning outcome of each assignment](#learning-outcome-of-each-assignment)
	1. [Course 1 - Foundations](#course-1---foundations)
		1. [Module 2 - Regression](#module-2---regression)
		2. [Module 3 - Classification](#module-3---classification)
		3. [Module 4 - Clustering & Similarity](#module-4---clustering--similarity)
		4. [Module 5 - Recommender Systems](#module-5---recommender-systems)
		5. [Module 6 - Deep Learning](#module-6---deep-learning)

# Overview
This specialization, developed by researchers at the University of Washington, provides an introduction to the field of Machine Learning.

Through a series of case studies, participants will gain practical experience in key areas of Machine Learning, including prediction, classification, clustering, and information retrieval.

The program covers techniques for analyzing large and complex datasets, developing adaptive systems, and creating applications capable of making data-driven predictions.

Throughout the specialization, learners will implement and apply machine learning algorithms for prediction, classification, clustering, and information retrieval using real datasets.

Participants will gain hands-on experience with applied machine learning concepts and Python programming.

# Getting Started on a python environment
To complete the course, I chose to install MambaForge on a portable USB, and set up a python virtual environment there. Working with TuriCreate and Sframes. You are welcome to use any ML tool for this course instead. And even if you chose to work directly on your computer you'll still find the following step-by-step guide helpful

1- The USB needs ext4 filesystem

2- Get the latest MamabaForge release for your OS from [https://github.com/conda-forge/miniforge/releases]
```shell
bash THE_DOWNLOADED_SCRIPT -b -p NEW_FOLDER_TO_INSTALL_MAMBA
```

3- Initialise Mamba/Conda
```shell
mamba shell init
```

4- Create a virtual environment with jupyter and python 3.8 (for turicreate)
```shell
mamba create -n ml python=3.8 jupyter -y
```

5- Install TuriCreate inside the virtual environment
```shell
mamba activate ml
pip install turicreate
```
6- path turicreate's _plot.py (optional)

In recent pandas versions, `display.max_colwidth=-1` is invalid. It used to mean "no limit", but now pandas only accepts None. As Turicreate is dicontinued you need to manually change `mamba/envs/ml/lib/python3.8/site-packages/turicreate/visualization/_plot.py` on line `476` from `-1` to `None`. That is in order for `explore()` method to work normal.


7- Run Jupyter isnide your notebooks folder
```shell
jupyter notebook
```

## Notes
1- ```Miniconda/Ananconda``` are a pain in the ass for a portable USB

2- In step 3, you can instead ```source /media/$USER/$USB_NAME/Mamba/etc/profile.d/conda.sh``` but you got to do it each time

3- The last python version supported by TuriCreate is ```python 3.8```, and Mamba can't find TC, so it needs to be installed separately

4- Step 5 will take minutes to complete

5- To see your current env run ```mamba info --envs``` (it's indicated with a *)

6- ```mamba deactivate``` when you're done

# Learning outcome of each assignment
## Course 1 - Foundations
### Module 2 - Regression
- Execute programs with the Jupyter notebook
- Load and transform real, tabular data
- Compute summaries and statistics of the data
- Build a regression model using features of the data
### Module 3 - Classification
- Execute sentiment analysis code with the Jupyter notebook
- Load and transform real, text data
- Using the .apply() function to create new columns (features) for our model
- Compare results of two models, one using all words and the other using a subset of the words
- Compare learned models with majority class prediction
- Examine the predictions of a sentiment model 
- Build a sentiment analysis model using a classifier
### Module 4 - Clustering & Similarity
- Execute document retrieval code with the Jupyter notebook
- Load and transform real, text data
- Compare results with word counts and TF-IDF
- Set the distance function in the retrieval
- Build a document retrieval model using nearest neighbor search
### Module 5 - Recommender Systems
- Execute song recommendation code with the Jupyter notebook
- Load and transform real, song data
- Build a song recommender model
- Use the model to recommend songs to individual users
- Use groupby to compute aggregate statistics of the data
### Module 6 - Deep Learning
- Load and transform real image data
- Use the Sketch method to view statistics of data
- Build image retrieval models using nearest neighbor search and deep features
- Compare the results of various image retrieval models
- Use the apply and sum methods to compute functions of the data