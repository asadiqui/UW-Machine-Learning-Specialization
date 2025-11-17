# Table of Contents
- [Overview](#overview)
- [Tools I used to complete the specialization](#tools-i-used-to-complete-the-specialization)
	- [Important Update](#important-update)
	- [Getting Started on a python environment](#getting-started-on-a-python-environment)
		- [Notes](#notes)
- [Learning outcome of each assignment](#learning-outcome-of-each-assignment)
	- [Course 1 - Foundations](#course-1---foundations)
		- [Module 2 - Regression](#module-2---regression)
		- [Module 3 - Classification](#module-3---classification)
		- [Module 4 - Clustering & Similarity](#module-4---clustering--similarity)
		- [Module 5 - Recommender Systems](#module-5---recommender-systems)
		- [Module 6 - Deep Learning](#module-6---deep-learning)
	- [Course 2 - Regression](#course-2---regression)
		- [Module 2 - Simple Regression](#module-2---simple-regression)

# Overview
This specialization, developed by researchers at the University of Washington, provides an introduction to the field of Machine Learning.

Through a series of case studies, participants will gain practical experience in key areas of Machine Learning, including prediction, classification, clustering, and information retrieval.

The program covers techniques for analyzing large and complex datasets, developing adaptive systems, and creating applications capable of making data-driven predictions.

Throughout the specialization, learners will implement and apply machine learning algorithms for prediction, classification, clustering, and information retrieval using real datasets.

Participants will gain hands-on experience with applied machine learning concepts and Python programming.

# Tools I used to complete the specialization
To complete the course, I chose to install MambaForge on a portable USB, and set up a python virtual environment there. You are welcome to use any ML tool.

- **Miniforge** for python environment, a Conda installer for the commands `conda` and `mamba` that comes without the default Anaconda packages.
- **SFrame** for data manipulation, an open-source, highly-scalable Python library for data manipulation included as part of the Turi Create library. The SFrame API is very similar to **Pandas**' API.
- **Numpy** for matrix operations, an open-source Python library that provides fast performance, for data that fits in memory.
- **Matplotlib** for plotting, an open-source Python library with extensive plotting functionality.
- **Turi Create** for pre-implemented ML algorithms (only in fundamental assignments), an open-source package that has seen an exciting adoption curve, especially in industry with folks building real applications.

## Important Update
After completing the foundations course and doing a technical interview with Oracle (which I failed), I realised that many of the suggested tools are abandoned by the industry, here is the stack I migrated to:
- Data Manipulation: SFrame -> **Pandas** (must-know skill)
- Matrix Operations: **Numpy** (universal)
- Plotting: Matplotlib -> **Seaborn** (built on Matplotlib)
- ML Library: TuriCreate -> **Scikit-learn** (industry standard for classical ML)

## Getting Started on a python environment
Even if you chose to work directly on your computer, a virtual environment is strongly recommended in order to avoid potential conflicts with other packages.

1- The USB needs ext4 filesystem

2- Get the latest Miniforge release for your OS from [https://github.com/conda-forge/miniforge/releases]
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
6- patch turicreate's _plot.py (optional)

In recent pandas versions, `display.max_colwidth=-1` is invalid. It used to mean "no limit", but now pandas only accepts None. As Turicreate is dicontinued you need to manually change `mamba/envs/ml/lib/python3.8/site-packages/turicreate/visualization/_plot.py` on line `476` from `-1` to `None`. That is in order for `explore()` method to work normal.


7- Run Jupyter isnide your notebooks folder
```shell
jupyter notebook
```

### Notes
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
- **Build a regression model using features of the data**
### Module 3 - Classification
- Execute sentiment analysis code with the Jupyter notebook
- Load and transform real, text data
- Using the .apply() function to create new columns (features) for our model
- Compare results of two models, one using all words and the other using a subset of the words
- Compare learned models with majority class prediction
- Examine the predictions of a sentiment model 
- **Build a sentiment analysis model using a classifier**
### Module 4 - Clustering & Similarity
- Execute document retrieval code with the Jupyter notebook
- Load and transform real, text data
- Compare results with word counts and TF-IDF
- Set the distance function in the retrieval
- **Build a document retrieval model using nearest neighbor search**
### Module 5 - Recommender Systems
- Execute song recommendation code with the Jupyter notebook
- Load and transform real, song data
- **Build a song recommender model**
- Use the model to recommend songs to individual users
- Use groupby to compute aggregate statistics of the data
### Module 6 - Deep Learning
- Load and transform real image data
- Use the Sketch method to view statistics of data
- **Build image retrieval models using nearest neighbor search and deep features**
- Compare the results of various image retrieval models
- Use the apply and sum methods to compute functions of the data

## Course 2 - Regression
### Module 2 - Simple Regression
- Use SArray and SFrame functions to compute important summary statistics
- Write a function to compute the Simple Linear Regression weights using the closed form solution
- Write a function to make predictions of the output given the input feature
- Turn the regression around to predict the input/feature given the output
- **Compare two different models for predicting house prices**