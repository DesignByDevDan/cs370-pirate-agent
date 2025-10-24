# CS 370 – Pirate Intelligent Agent (Treasure Hunt Game)

This repository contains my Project Two notebook implementing a **deep Q-learning** agent (the pirate) that learns to navigate an 8×8 maze to reach the treasure.

## What code was given vs. what I wrote
- **Provided:** `TreasureMaze.py` (environment, rewards, transitions), `GameExperience.py` (experience replay), and the Jupyter notebook scaffold with helper functions (`show`, `play_game`, `completion_check`, `build_model`).
- **I implemented/modified:**
  - Completed the **`qtrain`** (deep Q-learning) loop: epsilon-greedy policy, valid-action masking, replay sampling, Keras training, and a 100% win-rate stopping check.
  - Made it robust to minor API differences (e.g., state shapes `(1, N)` vs `(N,)`, replay buffer access, and `get_data` signatures).
  - Fixed shape/attribute issues (no `rows/cols` on env; normalized states; stored transitions as `(1, N)` for `GameExperience`).
  - Logged epoch metrics and ensured completion check passes from all valid start cells.

## Connecting my learning to the larger field of CS

### What do computer scientists do and why does it matter?
Computer scientists design, analyze, and build computational systems that **solve real problems at scale**—from routing robots and self-driving cars to optimizing logistics and healthcare triage. This project reflects that mindset by turning a vague task (“find treasure efficiently”) into a **formal problem** with states, actions, rewards, and an optimization objective.

### How do I approach a problem as a computer scientist?
1. **Specify the problem:** Define states, actions, transitions, and rewards in the maze.
2. **Select a method:** Use **reinforcement learning** (deep Q-learning) to learn a policy from experience rather than hard-coding rules.
3. **Iterate and evaluate:** Train with replay, monitor loss/win-rate, and validate with a completion check from multiple start states.
4. **Debug & generalize:** Handle edge cases (state shapes, API differences) and make the solution maintainable and reproducible.

### What are my ethical responsibilities to the end user and the organization?
- **Safety & reliability:** Ensure the agent behaves predictably; verify with completion checks and constraints.
- **Transparency:** Document assumptions, reward design, and limitations of the learned policy.
- **Fairness & accountability:** Avoid reward structures that cause unintended behaviors (e.g., reward hacking); ensure results can be audited and reproduced.
- **Privacy/compliance (general RL/AI work):** When data is involved, respect data protection and institutional guidelines.

## How to run
1. Install requirements in your Python/Jupyter environment.
2. Open the notebook and run all cells. Training will print epoch logs and stop once it reaches sustained 100% wins and passes `completion_check`.
3. Use `play_game(model, qmaze, pirate_start)` to test the learned policy from `(0, 0)` and other free cells.

## Repository contents
- `TreasureHuntGame.ipynb` – main notebook (pirate intelligent agent).
- `README.md` – this file.
- Optional: `.gitignore` for Jupyter checkpoints and model files.

---
