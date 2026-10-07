BFS and DFS Grid Pathfinder

Project Overview

This project implements a Grid Pathfinder using two graph traversal algorithms:

- Breadth-First Search (BFS)
- Depth-First Search (DFS)

The system searches a rectangular grid from a designated start cell to a designated goal cell without crossing blocked cells.

The project also includes performance profiling of BFS and DFS to compare their execution behavior.

---

Objectives

The main objectives of this project are:

1. To implement Breadth-First Search (BFS).
2. To implement Depth-First Search (DFS).
3. To find a route between a start and goal cell.
4. To avoid blocked cells and repeated visits.
5. To reconstruct the discovered path.
6. To measure the execution performance of BFS and DFS.
7. To generate profiling information and flame graphs.

---

Project Structure

IAI_SLE2_BFS_DFS/
│
├── bfs.py
├── dfs.py
│
├── profile_bfs.py
├── profile_dfs.py
│
├── bfs_for_pyspy.py
├── dfs_for_pyspy.py
│
├── bfs_profile.svg
├── dfs_profile.svg
│
├── README.md
└── CONTRIBUTING.md

---

System Architecture

The project follows the C4 architecture model:

User
  │
  ▼
BFS / DFS Grid Pathfinder
  │
  ├── Input Module
  │
  ├── Search Engine
  │     ├── BFS
  │     └── DFS
  │
  ├── Visited Set
  │
  ├── Path Builder
  │
  └── Output / Performance Results

---

BFS

Breadth-First Search explores the graph level by level.

BFS uses a queue and follows the FIFO (First In, First Out) principle.

Start
  ↓
Explore nearby cells
  ↓
Explore next level
  ↓
Continue until goal

For an unweighted grid, BFS can find the shortest path when the goal is reached.

---

DFS

Depth-First Search explores one branch as deeply as possible before backtracking.

DFS uses a stack or recursion and follows the LIFO (Last In, First Out) principle.

Start
  ↓
Go deeper
  ↓
Continue along current path
  ↓
Backtrack when required
  ↓
Continue searching

---

Main Functions

"generate_maze(size)"

Creates the grid/maze used by the search algorithms.

"bfs(maze, start, end)"

Performs Breadth-First Search using a queue.

"dfs(maze, start, end)"

Performs Depth-First Search using a stack/DFS traversal.

Parent Dictionary

The parent dictionary records how a cell was reached.

Current Cell → Parent Cell

It is used to reconstruct the final route.

---

Path Reconstruction

After the goal is found, the system follows the stored parent links backward:

GOAL
  ↓
Parent
  ↓
Parent
  ↓
START

The path is then reversed to obtain the route from START to GOAL.

---

Performance Profiling

The project contains separate profiling scripts for BFS and DFS:

profile_bfs.py
profile_dfs.py

These scripts are used to measure the execution performance of the algorithms.

Py-Spy profiling is also included:

bfs_for_pyspy.py
dfs_for_pyspy.py

The resulting flame graphs are:

bfs_profile.svg
dfs_profile.svg

---

Technologies Used

- Python
- Git
- GitHub
- BFS
- DFS
- Py-Spy
- SVG Flame Graphs

---

How to Run

Run BFS

python bfs.py

Run DFS

python dfs.py

Run BFS Profiling

python profile_bfs.py

Run DFS Profiling

python profile_dfs.py

---

Expected Output

The program performs graph/grid traversal and produces:

- Traversal/search result
- Path information
- BFS/DFS execution information
- Profiling results

The profiling files can be viewed to understand which parts of the program consume execution time.

---

C4 Architecture

The project is described using four C4 levels:

Level 1 — Context

Shows the user and the BFS/DFS Grid Pathfinder system.

Level 2 — Container

Shows the major modules:

- Input Module
- Search Engine
- Visited Set
- Output Module
- Performance Profiling

Level 3 — Component

The Search Engine contains:

- Frontier
- Explored Set
- Goal Test
- Path Builder
- Parent Dictionary
- Neighbour Expansion

Level 4 — Code

The implementation contains functions and structures such as:

generate_maze()
bfs()
dfs()
parent dictionary
path reconstruction loop

---

Conclusion

This project demonstrates how BFS and DFS can be applied to a grid pathfinding problem. It also provides performance profiling to study the behavior of the two search algorithms.

The main structural difference between BFS and DFS is the frontier: BFS uses a queue, while DFS uses a stack/recursive traversal.
