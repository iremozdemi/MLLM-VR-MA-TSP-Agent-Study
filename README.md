# MLLM-VR-MA-TSP-Agent-Study
MLLM-VR-MA-TSP-Agent-Study
```python
def generate_prompt_vrp(num_salesmen, points, depot_index, demands=None, capacity=None):
    ...
```
# LLM-Based Multi-Agent Vehicle Routing Framework

## Overview

This repository contains the implementation of a Large Language Model (LLM)-based multi-agent framework for solving the Vehicle Routing Problem (VRP).

Instead of relying purely on traditional mathematical optimization techniques, the system leverages structured prompt engineering to guide the LLM in generating approximate routing solutions through logical reasoning.

The framework is designed for experimental comparison between multiple agent strategies.

---

## Problem Definition

Given:

- A set of customer coordinates
- A depot location
- A predefined number of salesmen (vehicles)
- Optional customer demands
- Optional vehicle capacity constraints

Each salesman must:

1. Start from the depot
2. Visit a subset of customers
3. Return to the depot
4. Ensure all customers are visited exactly once

---

## Prompt Generation Module

The core component of this repository is the `generate_prompt_vrp` function, which constructs structured prompts for the LLM.

### Function Signature

```python
def generate_prompt_vrp(num_salesmen, points, depot_index, demands=None, capacity=None):
```

### Description

This function dynamically generates a natural language prompt containing:

- Number of salesmen
- Depot index
- Customer coordinates
- Optional demand information
- Optional vehicle capacity constraint
- Explicit routing format instructions

The generated prompt instructs the LLM to:

- Produce approximate VRP solutions
- Avoid formal optimization algorithms
- Output routes in a structured format (e.g., `Salesman 1: 0 -> 3 -> 4 -> 0`)
- Ensure feasibility (all customers visited exactly once)

---

## Example Usage

```python
prompt = generate_prompt_vrp(
    num_salesmen=2,
    points=points_array,
    depot_index=0,
    demands=[2, 3, 4, 1],
    capacity=10
)

print(prompt)
```

---

## Research Contribution

This implementation supports experimental evaluation of:

- LLM reasoning capability in combinatorial optimization
- Prompt engineering effectiveness in structured routing problems
- Multi-agent strategy comparison

The repository is intended to accompany an academic study evaluating LLM-driven VRP heuristics.

---

## Requirements

- Python 3.9+
- NumPy
- Access to an LLM API (API key must be set as an environment variable)

---

## API Key Setup

Make sure to configure your API key as an environment variable:

```bash
export API_KEY="your_api_key_here"
```

If the API key is not found, the program will raise:

```
API key not found. Please set the environment variable.
```

---

## License

MIT License
