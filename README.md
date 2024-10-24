# Schelling's Model of Segregation

## Introduction
This project implements Schelling's Model of Segregation. The model simulates the behavior of two distinct groups in a population, aiming to study patterns of segregation based on their preferences for similar neighbors. Each group, represented by agents on a grid, decides to stay or move based on how satisfied they are with their neighbors. The model aims to explore how even mild preferences for similar neighbors can lead to complete segregation over time.

## Model Overview
Schelling’s Model of Segregation is based on a grid representing a population of agents divided into two groups. Agents are satisfied when a certain proportion of their neighbors belong to the same group. If not satisfied, agents move to a randomly selected vacant space. The simulation runs iteratively, with agents checking their satisfaction and moving if necessary, until all agents are satisfied or a set number of iterations are reached.

### Key Concepts
- **Agents**: Represented by 1 or 2 for two groups, and 0 for vacant spaces.
- **Grid**: The NxN grid represents the environment in which agents reside.
- **Satisfaction Threshold (t)**: The proportion of similar neighbors required for an agent to remain satisfied.
- **Vacant Spaces (E)**: A percentage of the grid cells that are left empty, allowing space for agents to move.

## Tasks

### Task 1: Initialize the Grid
The first task is to set up the grid environment for the simulation. The grid has a size of NxN, and a certain proportion of the cells are vacant. The rest of the cells are filled with agents from two groups (Group 1 and Group 2), with an equal number of agents from each group randomly distributed across the grid. The initialization adds padding to the grid (with an additional row and column of zeros) to simplify boundary conditions. This task ensures the grid is correctly populated before running the simulation.

### Task 2: Identify Unhappy Agents
Agents become unhappy if the proportion of their neighbors who belong to the same group falls below a given satisfaction threshold, t. The task here is to identify the positions of all unhappy agents. An agent checks its immediate neighborhood (8 surrounding cells) and calculates the fraction of similar neighbors. If the fraction is less than t, the agent is considered unhappy. The list of unhappy agents is then used for future moves.

### Task 3: Identify Vacant Cells
This task identifies the positions of all vacant cells on the grid. Vacant cells (denoted by 0) are the locations to which unhappy agents can move. These vacant spaces are essential for ensuring agents have space to relocate during the simulation.

### Task 4: Move Unhappy Agents
Unhappy agents move to a randomly selected vacant cell. The task involves selecting agents from the list of unhappy ones and assigning them to a new location. To ensure randomness in both agent movement and the choice of vacant cells, the list of unhappy agents is shuffled before moving, and vacant cells are chosen at random. After moving, the agent's previous cell becomes vacant.

### Task 5: Simulate the Model
The simulation runs iteratively, updating the grid by checking for unhappy agents, moving them to vacant cells, and repeating until all agents are satisfied or a maximum number of iterations is reached. The simulation function initializes the grid and repeatedly checks for unhappy agents, moving them as needed, until no further moves are required. The model returns a boolean indicating whether all agents were satisfied within the maximum number of iterations.

### Task 6: Find the Minimum Proportion of Vacant Spaces
In this final task, the objective is to identify the minimum proportion of vacant spaces (E) required to achieve satisfaction for at least 95% of simulation runs across different values of satisfaction thresholds (t). For each threshold (t) in the range [0.5, 0.75], the simulation is repeated 20 times with varying proportions of vacant spaces. The goal is to find the smallest value of E that ensures all agents are satisfied in at least 95% of simulations within 60 iterations.

### Simulation Parameters
- **Grid Size (N)**: 30x30 grid, accommodating up to 900 agents.
- **Satisfaction Thresholds (t)**: Values between 0.5 and 0.75, representing varying degrees of tolerance for dissimilar neighbors.
- **Vacant Space Proportions (E)**: Range from 0.1 to 0.4, representing different levels of available empty space in the grid.
- **Iterations**: Agents can move once per iteration, with a maximum of 60 iterations allowed (equivalent to 5 years in the simulation).

## Conclusion
Schelling's Model of Segregation demonstrates how even mild preferences for similar neighbors can result in large-scale segregation. By adjusting the satisfaction threshold and the proportion of vacant spaces, this project explores the dynamics of population movement and the emergence of patterns over time. The final task focuses on determining the minimum amount of empty space needed to maintain a harmonious society where agents are satisfied within a reasonable number of iterations.
