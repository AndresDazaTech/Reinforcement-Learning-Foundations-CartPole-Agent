# 🧠 Reinforcement Learning Foundations: CartPole Agent

[![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org/)
[![Gymnasium](https://img.shields.io/badge/Environment-Gymnasium-00bbff?style=flat-square)](https://gymnasium.farama.org/)
[![RL](https://img.shields.io/badge/Algorithm-Q--Learning-orange?style=flat-square)](https://en.wikipedia.org/wiki/Q-learning)

## 📌 Overview
This project demonstrates the fundamental concepts of **Reinforcement Learning (RL)** by training an agent to balance a pole in the classic `CartPole-v1` environment. The project compares a **Random Agent** (baseline) against a **Q-Learning Agent**, highlighting how learning from reward feedback leads to significant performance improvement over time.

This lab provides hands-on experience with the RL feedback loop—**state, action, reward, and policy update**—and connects these ideas to modern AI systems trained using Reinforcement Learning from Human Feedback (RLHF).

---

## 🎯 Learning Objectives
*   **Understand** the core reinforcement learning loop.
*   **Observe** the contrast between random behavior and learned policies.
*   **Implement** a tabular Q-Learning agent with a discretized state space.
*   **Analyze** training dynamics, exploration vs. exploitation, and learning curves.
*   **Connect** classical RL concepts to Large Language Models (LLMs) and modern agent design.

---

## 🕹️ Environment: CartPole-v1 (Gymnasium)
The goal is to keep a pole balanced upright by moving a cart left or right.

### State Space
The agent observes four continuous variables:
1.  **Cart Position**
2.  **Cart Velocity**
3.  **Pole Angle**
4.  **Pole Angular Velocity**

### Action Space
*   `0`: Push cart left
*   `1`: Push cart right

### Reward System
*   **+1 reward** for every time step the pole remains upright.
*   **Max Score:** 500 per episode.

---

## 🧪 Project Structure

### Part 1: Random Agent (Baseline)
*   The agent selects actions randomly.
*   **Key Observation:** Without learning, the agent fails almost immediately.
*   **Average Score:** ~20.

### Part 2: Q-Learning Agent
*   **Algorithm:** Implements a tabular Q-Learning algorithm.
*   **Discretization:** Since the state space is continuous, the agent maps observations into "bins" to create a manageable Q-table.
*   **Policy:** Uses **Epsilon-Greedy** exploration (ε) with decay over 500 episodes.
*   **Average Score (Last 50 episodes):** ~108 (Clear performance jump).

### 📈 Exploration Rate (ε) Experiment
I compared three different epsilon decay schedules to find the optimal balance between **Exploration** (trying new things) and **Exploitation** (using what was learned):

| Decay Rate | Behavior | Result |
| :--- | :--- | :--- |
| **0.990** | Fast Decay | Premature convergence; stopped learning too early. |
| **0.995** | **Original** | **Best Balance;** achieved consistent improvement. |
| **0.999** | Slow Decay | Too much exploration; prevented consistent learning. |

---

## 📊 Key Visualizations
The notebook generates plots that demonstrate:
1.  **Episode Score vs. Training Time:** Shows the volatile nature of RL.
2.  **Rolling Average Learning Curve:** Smoothes the scores to show the upward trend of the learned policy.
3.  **Epsilon Decay:** Visualizes how the agent shifts from random actions to smart actions over time.

---

## 💡 Reflection & AI Insights
This project reinforces several core principles used in modern AI:
*   **Reward Design:** The reward signal defines behavior. Poorly designed rewards lead to misaligned outcomes.
*   **Strategy:** Exploration is essential early on, but exploitation is critical for stability.
*   **RLHF Connection:** These principles are the foundation for training models like ChatGPT via Reinforcement Learning from Human Feedback (RLHF), where the model learns to align with human preferences through a reward model.

---

## 🛠️ Technologies Used
*   **Python**
*   **Gymnasium** (formerly OpenAI Gym)
*   **NumPy** (Data processing and Q-table math)
*   **Matplotlib** (Visualization)
*   **Jupyter / Google Colab**

---

## 🚀 How to Run
1.  Open the `.ipynb` file in **Google Colab** or **Jupyter Notebook**.
2.  Install the required dependencies:
    ```bash
    pip install gymnasium matplotlib numpy
    ```
3.  Run all cells sequentially.
4.  Review the printed outputs and the final performance plots.

---

## 👤 Author
**Andres Daza Catano**  
Houston Community College  
*Spring 2026*
