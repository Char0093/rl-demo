# Reinforcement Learning (Q-Learning GridWorld) Demo

An interactive, zero-dependency browser demonstration of **Tabular Q-Learning** navigating a customizable 2D GridWorld.

## 🚀 Live Demo & Usage

- **Local**: Open `index.html` directly in any web browser.
- **GitHub Pages**: You can enable GitHub Pages from your repository settings (Settings -> Pages -> Deploy from branch `main` / `root`) to view the interactive demo online.

---

## 🧠 Features

- **Interactive GridWorld**:
  - Draw walls, place traps/hazards, and adjust start and goal positions by clicking directly on the canvas.
  - Built-in environment presets: *Classic Maze*, *Cliff Walking*, *Narrow Bridge*, and *Empty Grid*.
- **Q-Learning Algorithm Visualization**:
  - Policy arrows displaying the greedy action ($\arg\max_a Q(s, a)$) for each grid cell in real-time.
  - State-value heatmap shading cells based on maximum expected future reward.
  - Animated agent ($\text{🤖}$) learning optimal routes.
- **Real-Time Controls**:
  - **Learning Rate ($\alpha$)**: Control update step magnitude.
  - **Discount Factor ($\gamma$)**: Adjust importance of long-term vs. immediate rewards.
  - **Exploration ($\epsilon$)**: Tune exploration vs. exploitation with optional decay.
  - **Step / Run / Fast Train**: Step through transitions individually or batch-train 100 episodes instantly to observe convergence.
- **Performance Tracking**:
  - Real-time HTML5 canvas chart tracking steps per episode and learning convergence.
  - Rolling average metrics and episode counters.

---

## 📐 Algorithm Overview

The agent updates its state-action value table according to the Bellman equation:

$$Q(s, a) \leftarrow Q(s, a) + \alpha \left[ r + \gamma \max_{a'} Q(s', a') - Q(s, a) \right]$$

- **State ($s$)**: Grid cell coordinate $(r, c)$
- **Actions ($a$)**: Up, Right, Down, Left
- **Step Cost**: $-0.04$ per step (encourages shortest path)
- **Wall Collision**: $-0.5$
- **Trap Penalty**: $-10.0$ (terminal)
- **Goal Reward**: $+10.0$ (terminal)
