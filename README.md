# Table of Contents
- [Overview](#overview)
- [Tools I used to complete the specialization](#tools-i-used-to-complete-the-specialization)
	- [Important Update](#important-update)
	- [Getting Started on a python environment](#getting-started-on-a-python-environment)
		- [Notes](#notes)
- [Assignments](#assignments)
	- [Course 1](#course-1---foundations)
	- [Course 2](#course-2---regression)

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

# Assignments

## Course 1 - Foundations
- Module 1 - Welcome : [SFrames](https://github.com/asadiqui/UW-Machine-Learning-Specialization/blob/main/c1%20-%20Foundations/m1%20-%20Welcome/people-wiki_assignment.ipynb)
- Module 2 - Regression : [Predicting house prices](https://github.com/asadiqui/UW-Machine-Learning-Specialization/blob/main/c1%20-%20Foundations/m2%20-%20Regression/regression_assignment.ipynb)
- Module 3 - Classification : [Analyzing product sentiment](https://github.com/asadiqui/UW-Machine-Learning-Specialization/blob/main/c1%20-%20Foundations/m3%20-%20Classification/classification_assignment.ipynb)
- Module 4 - Clustering & Similarity : [Retrieving Wikipedia articles](https://github.com/asadiqui/UW-Machine-Learning-Specialization/blob/main/c1%20-%20Foundations/m4%20-%20Clustering%20%26%20Similarity/clustering_assignment.ipynb)
- Module 5 - Recommender Systems : [Recommending songs](https://github.com/asadiqui/UW-Machine-Learning-Specialization/blob/main/c1%20-%20Foundations/m5%20-%20Recommender%20Systems/recsys_assignment.ipynb)
- Module 6 - Deep Learning : [Deep features for image retrieval](https://github.com/asadiqui/UW-Machine-Learning-Specialization/blob/main/c1%20-%20Foundations/m6%20-%20Deep%20Learning/deep_learning_assignment.ipynb)

## Course 2 - Regression
- Module 2 - Simple Linear Regression : [Fitting a simple linear regression model on housing data](https://github.com/asadiqui/UW-Machine-Learning-Specialization/blob/main/c2%20-%20Regression/m2%20-%20Simple%20Linear%20Regression/assignment.ipynb)
- Module 3 - Multiple Regression : [Exploring different multiple regression models for house price prediction](https://github.com/asadiqui/UW-Machine-Learning-Specialization/blob/main/c2%20-%20Regression/m3%20-%20Multiple%20Regression/assignment_1.ipynb)