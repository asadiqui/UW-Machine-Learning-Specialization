# Overview
This specialization, developed by researchers at the University of Washington, provides an introduction to the field of Machine Learning.

Through a series of case studies, participants will gain practical experience in key areas of Machine Learning, including prediction, classification, clustering, and information retrieval.

The program covers techniques for analyzing large and complex datasets, developing adaptive systems, and creating applications capable of making data-driven predictions.

Throughout the specialization, learners will implement and apply machine learning algorithms for prediction, classification, clustering, and information retrieval using real datasets.

Participants will gain hands-on experience with applied machine learning concepts and Python programming.

# Personal Guide
To complete the course, I chose to install MambaForge on a portable USB, and set up a python virtual environment there.

Even if you chose to work directly on your computer you'll find the following guide helpful

1- The USB needs ext4 filesystem

2- Get the latest MamabaForge release for your OS from [https://github.com/conda-forge/miniforge/releases]
```shell
bash THE_DOWNLOADED_SCRIPT -b -p NEW_FOLDER_TO_INSTALL_MAMBA
```

3- Initialise Mamba/Conda
```shell
mamba shell init
```

4- Create a virtual environemnt with jupyter and python 3.8 (for turicreate)
```shell
mamba create -n ml python=3.8 jupyter -y
```

5- Install TuriCreate inside the virtual environment
```shell
mamba activate ml
pip install turicreate
```

6- Run Jupyter isnide your notebooks folder
```shell
jupyter notebook
```

## NOTES
1- ```Miniconda/Ananconda``` are a pain in the ass for a portable USB

2- You can instead ```source /media/$USER/$USB_NAME/Mamba/etc/profile.d/conda.sh``` but you got to do it each time

3- The last python version supported by TuriCreate is ```python 3.8```, and Mamba can't find it, so it needs to be installed seperatly

4- Step 4 will take minutes to complete

5- To see your current env run ```mamba info --envs``` (it's indicated with a *)

6- ```mamba deactivate``` when you're done