# multiagent_collision_avoidance
This repository contains the implementation of
### Non-communicating Multi-Agent Collision Avoidance with Deep Reinforcement Learning

A two agent collision avoidance algorithm is implemented based on Deep Reinforcement Learning.

[<img src="https://www.linkpicture.com/q/000_learning_2agents.gif" width="620" height="480">](https://www.linkpicture.com/view.php?img=LPic627166333e1c31110223739)

[Multiagent gym environment](https://gym-collision-avoidance.readthedocs.io/en/latest/index.html) was used in this project to implement and validate the algorithm. 
The implementation was done in Python programming language, and
deep model was trained using Keras library and TensorFlow.

All the scripts are in the [experiments/src](https://github.com/atharva417/multiagent_collision_avoidance/tree/master/gym-collision-avoidance/gym_collision_avoidance/experiments/src)
folder.

Following python files were implemented:

[get_value_traj](https://github.com/atharva417/multiagent_collision_avoidance/blob/master/gym-collision-avoidance/gym_collision_avoidance/experiments/src/get_value_traj.py): This file contains the class GET_VALUE_TRAJ that accepts the value
network and the target value network and uses these to generate state trajectories
and target values (labels) for training

[value_training](https://github.com/atharva417/multiagent_collision_avoidance/blob/master/gym-collision-avoidance/gym_collision_avoidance/experiments/src/value_training.py): This file contains the main code for the training, it trains the value
network according to the above mentions algorithm and uses the get_value_traj ʨile
for the same. It also generates random training samples at each episode and saves
the ʨinal trained model weights at the end of the training

[get_traj](https://github.com/atharva417/multiagent_collision_avoidance/blob/master/gym-collision-avoidance/gym_collision_avoidance/experiments/src/get_traj.py): This file contains the class that accepts the value_network and outputs the
state trajectory. This ʨile is used for validation and evaluation of the performance of
the algorithm. No training is done in this ʨile. It’s just for testing the trained
networks.

[helper](https://github.com/atharva417/multiagent_collision_avoidance/blob/master/gym-collision-avoidance/gym_collision_avoidance/experiments/src/helper.py): This file contains several helper functions that are used throughout the project by different ʨiles. This contains functions to get feasible set of actions, query
the network to get the output value, get ʨiltered velocity, propagate the agents for
time ∆𝑡, get rewards and to get parameterized state vector from normal state vector.

[run_trajectory_dataset_creator](https://github.com/atharva417/multiagent_collision_avoidance/blob/master/gym-collision-avoidance/gym_collision_avoidance/experiments/src/run_trajectory_dataset_creator.py): This file is used to generate a set of 500 random trajectories. Some modification was made to this files
to convert the trajectories into parametrized (agent-centric) state vector, and save the correcponding state-value pairs.


For training part Deep Q-Learning with Experience Replay was used for improved stability and convergence.
