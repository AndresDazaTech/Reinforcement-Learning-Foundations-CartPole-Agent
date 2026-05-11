🧠 Reinforcement Learning Foundations: CartPole Agent
Overview
This project demonstrates the fundamental concepts of Reinforcement Learning (RL) by training an agent to balance a pole in the classic CartPole‑v1 environment. The project compares a random agent against a Q‑Learning agent, highlighting how learning from reward feedback leads to performance improvement over time.
The lab provides hands‑on experience with the RL feedback loop—state, action, reward, and policy update—and connects these ideas to modern AI systems trained using Reinforcement Learning from Human Feedback (RLHF).

Learning Objectives

Understand the core reinforcement learning loop
Observe the contrast between random behavior and learned policies
Implement a tabular Q‑Learning agent with discretized state space
Analyze training dynamics, exploration vs. exploitation, and learning curves
Connect classical RL concepts to large language models and agent design


Environment
CartPole‑v1 (Gymnasium)
State Space
The agent observes four continuous variables:

Cart position
Cart velocity
Pole angle
Pole angular velocity

Action Space

0: Push cart left
1: Push cart right

Reward

+1 reward for each time step the pole remains upright
Maximum score per episode: 500


Project Structure
Part 1: Random Agent (Baseline)

The agent selects actions randomly
Results in short episode durations and low average scores
Establishes a baseline for comparison

Key Observation:
Without learning, the agent fails almost immediately, with average scores around ~20.

Part 2: Q‑Learning Agent

Implements a tabular Q‑Learning algorithm
Discretizes the continuous state space into bins
Uses epsilon‑greedy exploration with decay over time
Trained for 500 episodes

Key Concepts:

Exploration vs. exploitation tradeoff
Reward‑driven policy improvement
Learning curves and convergence behavior

Results:

Random agent average score: ~18
Q‑Learning agent (last 50 episodes): ~108
Clear performance improvement over baseline


Exploration Rate Experiment
Three agents were compared:

Fast epsilon decay (ε = 0.990)
Original decay (ε = 0.995)
Slow decay (ε = 0.999)

Outcome:
The original decay schedule achieved the best balance.
Too little exploration led to premature convergence, while too much exploration prevented consistent learning.

Key Visualizations

Episode score vs. training time
Rolling average learning curve
Epsilon (exploration rate) decay
Comparative performance of different decay strategies

These plots visually demonstrate how learning emerges over time.

Reflection & AI Agent Design Insights
This project reinforces that:

The reward signal defines agent behavior
Poorly designed rewards can lead to misaligned or exploitable outcomes
Exploration is essential early on, but exploitation is critical later
Classical RL concepts directly map to RLHF, which is used to train modern LLMs

Understanding these principles is foundational for designing reliable, goal‑aligned AI agents—even when using high‑level frameworks or APIs.

Technologies Used

Python
Gymnasium
NumPy
Matplotlib
Jupyter / Google Colab


How to Run

Open the notebook in Google Colab or Jupyter
Install dependencies:
Shellpip install gymnasium matplotlib numpyShow more lines

Run all cells sequentially
Review printed outputs and generated plots


Author
Andres Daza Catano
Houston Community College
Spring 2026
