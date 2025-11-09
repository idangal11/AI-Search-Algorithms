# AI Search Algorithms – BFS & A*

## 📘 Overview
This project was developed as part of the **Introduction to Artificial Intelligence** course (Winter 2022/23) at **Ben-Gurion University of the Negev**.

The goal of this assignment is to implement and compare two classical search algorithms — **Breadth-First Search (BFS)** and **A\*** — for pathfinding in a 2D grid.  
Given a start and goal location on a grid, the algorithms must find a valid route for an autonomous vehicle while avoiding obstacles.

---

## 🚗 Problem Description
A self-driving car must navigate from a start location to a goal location on a given grid map.  
Each cell in the grid can represent either:
- An **open** cell (where movement is possible)
- A **blocked** cell (`@`) that cannot be traversed

The car can move **north, south, east, or west**, as long as the move stays within the grid and avoids blocked cells.

---

## 🧭 Algorithms Implemented

### 1. Breadth-First Search (BFS)
A uniform-cost, unweighted search that explores all neighboring states level by level.  
Implemented in `breadth_first_search.py`.

Key functions implemented:
- `init_open()`: Initialize the open data structure (queue).
- `insert_to_open(open_list, s)`: Insert a new state into the open list.
- `get_best(open_list)`: Retrieve the next best node (FIFO order).
- `get_neighbors(grid, s_location)`: Return valid adjacent states.
- `is_goal(s_location, goal_location)`: Check if the goal is reached.
- `check_for_duplicates_open(...)`, `check_for_duplicates_closed(...)`: Handle repeated states.

---

### 2. A* Search
A heuristic-based algorithm that balances exploration and exploitation.  
Implemented in `a_star_search.py`.

Key additional function:
- `calculate_heuristic(s_location, goal_location)`:  
  Estimates the distance from the current state to the goal (e.g., Manhattan distance).

The A* state includes:  
`(f, h, g, x, y, parent_state)`  
where:
- **f** = total estimated cost (g + h)  
- **g** = cost from start  
- **h** = heuristic estimate to goal  

---

## 🗂️ File Structure
