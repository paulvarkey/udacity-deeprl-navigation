# Navigation : Udacity DeepRL Nanondegree project

This codebase contains a solution to the Navigation project 
from Udacity's DeepRL Nanodegree.

## Project Details

## Setup

To set up your python environment to run the code in this repository, follow the instructions below.

1. Create (and activate) a new environment with Python 3.6.

	- __Linux__ or __Mac__ (pre Arm64 "Apple Silicon"):
	```bash
	conda create --name drlnd python=3.6
	source activate drlnd
	```
    - __Mac__ (Arm64 "Apple Silicon", ~2020 onwards):

    [[ref]](https://stackoverflow.com/a/70219965) Since Python 3.8 had been released for about a year when Apple Silicon hit the market, Python <=3.7 builds for osx-arm64 were never part of the regular build matrix for Conda Forge. One can create osx-64 environments like
	```bash
	## create empty environment
    conda create -n drlnd

    ## activate
    conda activate drlnd

    ## use x86_64 architecture channel(s)
    conda config --env --set subdir osx-64

    ## install python
    conda install python=3.6
	```
	- __Windows__: 
	```bash
	conda create --name drlnd python=3.6 
	activate drlnd
	```
	
2. Follow the instructions in [this repository](https://github.com/openai/gym) to perform a minimal install of OpenAI gym.  
	- Install the **box2d** environment group by following the instructions below : 
    ```bash
    pip install swig
    pip install box2d-py
    ```
	
3. Clone the repository (if you haven't already!), and navigate to the `python/` folder.  Then, install several dependencies.
```bash
git clone https://github.com/paulvarkey/udacity-deeprl-navigation.git
cd python
pip install .
```

4. Create an [IPython kernel](http://ipython.readthedocs.io/en/stable/install/kernel_install.html) for the `drlnd` environment.  
```bash
python -m ipykernel install --user --name drlnd --display-name "drlnd"
```

5. Before running code in a notebook, change the kernel to match the `drlnd` environment by using the drop-down `Kernel` menu. 

## Instructions
