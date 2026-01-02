# Neuroevolution with Gymnasium
## Lunar Lander experiments using SALGA

This repository contains a practical exploration of **neuroevolutionary methods** applied to the
`LunarLander-v2` environment from the **Gymnasium** library.

The project is structured as a progressive experiment:
from human control, to heuristic agents, and finally to a **neuroevolutionary agent**
whose neural controller parameters are optimized using **SALGA (Simple Adaptive Learning Genetic Algorithm)**.

---

## Repository structure

.
├── notebooks/
│ └── Gymnasium_alumno.ipynb
├── lunarlander_salga.py
├── requirements.txt
├── README.md
└── LICENSE


---

## Project overview

The goal of this project is to understand different ways of controlling an agent in a complex environment:

1. **Human control**  
   Manual interaction with the Lunar Lander environment to gain intuition about the task.

2. **Rule-based agent**  
   A handcrafted policy based on thresholds over the observation variables.

3. **Neuroevolutionary agent**  
   A neural controller (single-layer perceptron) whose weights and biases are evolved using SALGA.

Instead of using gradient-based reinforcement learning, this project focuses on **evolving neural network parameters directly**.

---

## Neuroevolution with SALGA

- The agent is represented by a **single-layer perceptron**
- Inputs: 8 (environment observations)
- Outputs: 4 (discrete action space)
- Weights and biases are encoded as a **real-valued chromosome**
- SALGA evolves a population of chromosomes using selection, mutation, and recombination

The fitness of each chromosome is computed by running a complete episode of the Lunar Lander environment
and measuring the accumulated reward.

The best chromosome found by SALGA is later loaded into the model and visualized in the notebook.

---

##  Notebook

### `Gymnasium_alumno.ipynb`

The notebook contains:
- Environment exploration and manual control
- Implementation of a heuristic policy
- Definition of the perceptron model
- Integration of a chromosome obtained with SALGA
- Evaluation and visualization of agent behavior

The notebook is intended for **educational purposes**.

---

## Running the neuroevolution

The file lunarlander_salga.py is designed to be executed by SALGA.

It defines:
-The neural controller (perceptron)
-The chromosome representation
-The fitness function used by SALGA

SALGA automatically searches for the optimal chromosome by repeatedly evaluating candidate solutions
using the defined fitness function.

---

## Installation

Clone the repository and install the dependencies:

```bash
pip install -r requirements.txt
