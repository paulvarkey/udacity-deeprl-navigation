# Navigation : Udacity DeepRL Nanondegree project

This codebase contains a solution to the Navigation project 
from Udacity's DeepRL Nanodegree. 

One may watch the [accompanying Youtube video](https://youtu.be/rwPu4LlBlqw) first to see
the highlights during training and evaluation.

The project report is found in [Report.md](Report.md).

The notebook [Navigation.ipynb](Navigation.ipynb) 
demonstrates the full solution end-to-end : 
training, checkpointing of weights, followed by watching the trained agent in action.

The trained model weights are in [checkpoint.pth](checkpoint.pth).

The rest of this README provides details on the project, and setup, training 
and evaluation instructions.

## Attribution

The model ([model.py](model.py)) and the DQN agent ([dqn_agent.py](dqn_agent.py)), as well as the `python` sub-directory, are all copied directly and as-is from the earlier provided solutions in the course, in the section on DQN.

The DQN training algorithm is also adapted from the prior provided examples, with some refactoring and modifications that were necessary to get it to work in this scenario (where the environment is from Unity and not the Gym environment from OpenAI.)

## Project Details

The project involves creating an agent that learns to autonomously navigate in the 
Banana Unity environment, which is a large square world, in which the agent collects 
bananas, and gets rewarded as described a little later below.

Unit Environments contain **_brains_** which are responsible for deciding the actions 
of their associated agents. Here we check for the first brain available, 
and set it as the default brain we will be controlling from Python.

The simulation contains a single agent that navigates a large environment. 
At each time step, it has four actions at its disposal:
- `0` - walk forward 
- `1` - walk backward
- `2` - turn left
- `3` - turn right

The state space has `37` dimensions and contains the agent's velocity, along with ray-based perception of objects around agent's forward direction.  A reward of `+1` is provided for collecting a yellow banana, and a reward of `-1` is provided for collecting a blue banana.

A successful agent is defined as one which is able to gain an average reward (over 100 episodes) of 13 or more.

## Getting Started

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

1. Open up [Navigation.ipynb](Navigation.ipynb) and ensure to change the kernel in the drop-down menu to the one build above (e.g. "drlnd"). Change `banana_app_file_name` to a value appropriate to the one on your environment. Run all the cells in the **Imports and definitions** section.

2. Optionally, perform training with hyperparameters of your choice (uncomment, edit parameters, if desired, and run!)

3. Optionally, load the trained checkpoint ([checkpoint.pth](checkpoint.pth)) and visualize the agent in action (uncomment and run!)
