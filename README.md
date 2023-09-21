# TSP-using-DFID


# Traveling Salesman Problem (TSP) Solver

This code implements a solution to the Traveling Salesman Problem (TSP) using Depth-First Iterative Deepening (DFID) search. The TSP is a classic optimization problem where the goal is to find the shortest possible route that visits a set of cities exactly once and returns to the starting city.

## Prerequisites

Before running the code, make sure you have the following:

- Python 3.x installed.
- The `math` and `sys` libraries are imported in your Python environment.

## Usage

To use this code to solve the TSP for a set of cities, follow these steps:

1. Define your list of cities as (x, y) coordinates in the `cities` variable. For example:

```python
cities = [(0, 0), (1, 2), (2, 4), (3, 1)]
```

2. Run the `dfid_tsp` function by calling it with your list of cities as an argument:

```python
best_path, best_len = dfid_tsp(cities)
```

3. The code will find the best path and its length and store them in `best_path` and `best_len`, respectively.

4. To get the total length of the best path (including the return to the starting city), use the following:

```python
total_length = best_len + distance(cities[0], cities[best_path[-1]])
```

5. The best path is stored in `best_path`. To complete the cycle, you can append the starting city (city 0) to it:

```python
best_path.append(0)
```

6. Finally, print the results:

```python
print("Best length:", total_length)
print("Best path:", best_path)
```

## Functions

- `distance(point1, point2)`: Calculates the Euclidean distance between two points represented as (x, y) tuples.
- `path_length(path, cities)`: Computes the total length of a given path that visits cities in the order specified by `path`.
- `check_goal_test(path, num_cities)`: Checks if a given path contains all the cities, including the starting city, exactly once.
- `dfs_tsp(cities, current_city, depth, path, best_path, best_len)`: The main depth-first search function that explores different paths to solve the TSP.
- `dfid_tsp(cities)`: Initiates the DFID search for the TSP and returns the best path and length.

## Example

```python
cities = [(0, 0), (1, 2), (2, 4), (3, 1)]
best_path, best_len = dfid_tsp(cities)
total_length = best_len + distance(cities[0], cities[best_path[-1]])
best_path.append(0)
print("Best length:", total_length)
print("Best path:", best_path)
```

## Note

The code has an issue in the `dfid_tsp` function where it initializes `best_path` and `best_len` as lists with a single `None` and `sys.float_info.max`, respectively. The correct initialization should be with actual values (e.g., `best_path = []` and `best_len = float('inf')`).

Feel free to modify and use this code for your own TSP problems!
```

This README provides a clear overview of the code, how to use it, and any potential issues or modifications that need to be made.
