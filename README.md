# Multi-Agent Vehicle Routing & TSP Optimization

This repository contains scripts for solving Vehicle Routing Problems (VRP) and Traveling Salesman Problems (TSP) using **Euclidean optimization** and AI-assisted route improvement via **Gemini AI**.

---

## Key Features

* **Euclidean Distance Optimization**
  Iteratively improves routes using Euclidean distance as the main optimization metric.

* **Opt-2 Swap Heuristic**
  Applies longest two-edge swap for escaping local minima in TSP routes.

* **Gemini AI Integration**
  Generates improved routes using AI-assisted prompt strategies.

* **Visualization**
  Generates Base64 images of the optimized routes.

---

## Important Functions

### `generate_prompt_vrp`

Generates a prompt for LLMs to solve multi-agent VRP problems.

```python
def generate_prompt_vrp(num_salesmen, points, depot_index, demands=None, capacity=None):
    """
    Generates a textual prompt for AI to optimize multi-agent VRP routes.

    Args:
        num_salesmen (int): Number of salesmen/agents.
        points (array-like): Coordinates of all points including depot.
        depot_index (int): Index of depot point.
        demands (list, optional): Demand at each location. Default is None.
        capacity (int, optional): Maximum capacity for each salesman. Default is None.

    Returns:
        str: Formatted LLM prompt.
    """
    ...
```

### Distance Calculation & Optimization

```python
calculate_total_euclidean_distance(cities_coords, route_list)
apply_longest_2_edges_opt2_swap(cities_coords, current_route, cycle_counter)
```

* `calculate_total_euclidean_distance`: Sum of Euclidean distances for a given route.
* `apply_longest_2_edges_opt2_swap`: Applies Opt-2 swap on the two longest disjoint edges of a route.

---

## Usage Example

```python
from vrp_module import generate_prompt_vrp, calculate_total_euclidean_distance

# Initial data
num_salesmen = 2
points = [[0,0], [1,2], [3,1], [2,4]]
deport_index = 0

# Generate LLM prompt
prompt = generate_prompt_vrp(num_salesmen, points, depot_index)

# Compute distance for initial route
route = [0, 1, 2, 3, 0]
distance = calculate_total_euclidean_distance(points, route)

print("Initial Route Distance:", distance)
print("Prompt for AI:\n", prompt)
```

> **Note:** Full TSP/VRP optimization scripts are in `tsp_optimization.py`. README shows only function signatures and usage examples to avoid rendering issues on GitHub/Colab.

---

## License

This project is licensed under **MIT License**. See [LICENSE](LICENSE) for details.

---

## References

* Gemini AI for iterative route optimization
* Numpy & Matplotlib for calculations and visualizations
* Open-source VRP/TSP heuristics (Opt-2 swap)
