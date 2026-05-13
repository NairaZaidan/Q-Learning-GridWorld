# Q-Learning Grid World Solver

This project implements a **Reinforcement Learning (RL)** agent that utilizes the **Q-Learning algorithm** to navigate a 2D grid environment. The agent learns to navigate from a starting coordinate to a goal state while avoiding specific obstacles and staying within the boundaries of the grid.

## Project Overview

The environment is a 5x5 grid where the agent learns through iterative interaction to maximize its cumulative rewards. This implementation demonstrates fundamental RL concepts such as the exploration-exploitation trade-off using the Epsilon-Greedy strategy.

### Environment Specifications
* **Grid Size**: 5x5.
* **Start State**: (0, 0).
* **Goal State**: (4, 4).
* **Obstacles**: Located at (1, 1), (2, 2), and (3, 1).
* **Actions**: The agent can perform four discrete actions:
    * **0**: Left
    * **1**: Right
    * **2**: Up
    * **3**: Down

---

## Algorithm & Implementation

### Q-Learning Update Rule
The agent's knowledge is stored in a Q-Table of shape (5, 5, 4) and updated using the standard Q-Learning equation:

$$Q(s, a) \leftarrow Q(s, a) + \alpha [R + \gamma \max_{a'} Q(s', a') - Q(s, a)]$$

### Hyperparameters
The model was trained over 2,000 episodes using the following parameters:
* **Learning Rate ($\alpha$)**: 0.1.
* **Discount Factor ($\gamma$)**: 0.65.
* **Exploration Rate ($\epsilon$)**: Starts at 1.0 with a decay rate of 0.995 per episode, reaching a minimum of 0.01.
* **Episodes**: 2,000.

### Reward Structure
* **Goal Reached**: +10 (Terminal state).
* **Obstacle Hit**: -10 (Terminal state).
* **Normal Step**: -1 (Penalty to encourage efficiency).

---

## Results and Visualizations

### Final Performance
* **Path Efficiency**: After training, the agent reached the goal in 8 steps.
* **Successful Path**: The final learned trajectory is: `[(0, 0), (0, 1), (0, 2), (0, 3), (0, 4), (1, 4), (2, 4), (3, 4), (4, 4)]`.
* **Final Reward**: The agent achieved a final reward of 10 upon reaching the goal.

### Visualizations
The project includes several visualizations to track the agent's progress:
1. **Learning Curve**: A plot showing the total reward per episode, illustrating the agent's convergence over time.
2. **Path Grid**: A visual representation of the grid showing the Start (S), Goal (G), Obstacles (X), and the agent's optimized path (*).

---

## Project Structure

* `Q_learning.ipynb`: The primary Jupyter Notebook containing the environment setup, training loop, and visualization code.
* `README.md`: Project documentation.
