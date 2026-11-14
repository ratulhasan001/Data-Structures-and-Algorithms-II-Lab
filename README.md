# algorithms-lab

C++ solutions for the Data Structures and Algorithms II sessional (lab) course of the B.Sc. in Computer Science and Engineering at BAUET, written between December 2023 and early 2024. The lab sheets (`_lab.txt`) list the course as *CSE 2214 – Data Structures and Algorithms-II Sessional* (the Lab 1 sheet says CSE 2213). The labs start with the C++ STL (`vector`, `set`, `stack`, `map`) and move on to sorting, graph traversal, shortest paths, minimum spanning trees, and greedy and dynamic programming algorithms. Each program reads its input from standard input and writes to standard output.

## Contents

Experiment titles and dates come from the `_lab.txt` sheet in each folder. Labs 10–12 are not in the repository.

### [lab-01](lab-01) – Uses of STL (vector), 28 Dec 2023

| File | What it does |
|---|---|
| [Lab_01_28_12_23.cpp](lab-01/Lab_01_28_12_23.cpp) | Basic `vector` operations: reads `n` values with `push_back`, prints them, and prints `capacity()`. |
| [can_it_be_sorted.cpp](lab-01/can_it_be_sorted.cpp) | Checks whether the numbers can be rearranged into a run of consecutive integers (sort, then compare neighbours), O(n log n). |
| [find_substring.cpp](lab-01/find_substring.cpp) | Prints TRUE if the second string occurs in the first, using `std::string::find`. Note: this is a substring test, not the "every letter appears" check described on the lab sheet. |
| [smaller_than_left_right.cpp](lab-01/smaller_than_left_right.cpp) | Prints the elements that are strictly smaller than both neighbours, O(n). |
| [_lab.txt](lab-01/_lab.txt), [Lab_01_28_12_23_Note.txt](lab-01/Lab_01_28_12_23_Note.txt) | Lab sheet and short class notes on the STL. |

### [lab-02](lab-02) – Uses of STL (set), 4 Jan 2024

| File | What it does |
|---|---|
| [Lab_02_04_01_24.cpp](lab-02/Lab_02_04_01_24.cpp) | Answers `q` queries on a `std::set`: 1 = insert, 2 = erase, 3 = membership test. O(log n) per query. |

### [lab-03](lab-03) – Uses of STL (stack), 11 Jan 2024

| File | What it does |
|---|---|
| [lab_3_11_01_2024.cpp](lab-03/lab_3_11_01_2024.cpp) | Basic `stack` operations: pushes strings, prints them in LIFO order, pops `x` items from a second copy and prints the top. |
| [remove_last_k_digits_of_a_number.cpp](lab-03/remove_last_k_digits_of_a_number.cpp) | Removes the last K digits of a number using two stacks of digits. |
| [balanced_brackets.cpp](lab-03/balanced_brackets.cpp) | Checks whether a string of `()[]{}` brackets is balanced using a stack, O(n). |
| [balance_three_stacks_maxSum.cpp](lab-03/balance_three_stacks_maxSum.cpp) | Pops from the stack with the largest sum until all three stacks have equal sums, then prints that maximum common sum. |
| [map_problem.cpp](lab-03/map_problem.cpp) | Reads `(int, char)` pairs into a `map<int, char>` (later keys overwrite) and counts how often each character appears. |

### [lab-04](lab-04) – Quick Sort and BFS, 18 Jan 2024

| File | What it does |
|---|---|
| [quickSort.cpp](lab-04/quickSort.cpp) | Quick sort with Lomuto partition (last element as pivot). Average O(n log n), worst case O(n²). |
| [bfs.cpp](lab-04/bfs.cpp) | Breadth-first search on an undirected graph (adjacency list), printing the visit order. O(V + E). |

### [lab-05](lab-05) – Merge Sort and DFS, 25 Jan 2024

| File | What it does |
|---|---|
| [merge_sort.cpp](lab-05/merge_sort.cpp) | Top-down merge sort with temporary left/right arrays. O(n log n) time, O(n) extra space. |
| [dfs.cpp](lab-05/dfs.cpp) | Iterative graph traversal with an explicit stack on an undirected graph, printing the visit order. O(V + E). |

### [lab-06](lab-06) – Dijkstra's algorithm, 1 Feb 2024

| File | What it does |
|---|---|
| [dijkstra.cpp](lab-06/dijkstra.cpp) | Dijkstra's algorithm with a min-heap priority queue on a weighted undirected graph. Prints the distance to every node and the shortest path from the source to node `n`. O((V + E) log V). |

### [lab-07](lab-07) – Kruskal's algorithm, 8 Feb 2024

| File | What it does |
|---|---|
| [kruskal.cpp](lab-07/kruskal.cpp) | Kruskal's minimum spanning tree: sorts the edges and uses a disjoint-set union (union by size) to print the MST edges. O(E log E). |
| [dijkstra.cpp](lab-07/dijkstra.cpp) | Same Dijkstra implementation as Lab 6, printing distances only. |

### [lab-08](lab-08) – Bellman–Ford algorithm, 15 Feb 2024

| File | What it does |
|---|---|
| [bellman_ford.cpp](lab-08/bellman_ford.cpp) | Bellman–Ford single-source shortest paths from node 1 over a list of directed edges (V − 1 relaxation rounds). O(V·E). Does not check for negative cycles. |

### [lab-09](lab-09) – Floyd–Warshall

| File | What it does |
|---|---|
| [floyd_warshall.cpp](lab-09/floyd_warshall.cpp) | Floyd–Warshall all-pairs shortest paths on a fixed 4 × 4 adjacency matrix read from input (`999` means no edge). O(V³). An earlier version is kept, commented out, at the top of the file. |

### [lab-13](lab-13) – Backtracking

| File | What it does |
|---|---|
| [four_queen_problem.cpp](lab-13/four_queen_problem.cpp) | **Incomplete.** Starts a 4-Queens backtracking solution (board printer and a partial `isSafe` check), but `main` is empty, so it prints nothing. |

### [lab-final](lab-final) – Lab final practice

| File | What it does |
|---|---|
| [0_1_knapsack.cpp](lab-final/0_1_knapsack.cpp) | 0/1 knapsack by plain recursion (include or skip each item). O(2ⁿ) without memoisation. |
| [fractional.cpp](lab-final/fractional.cpp) | Greedy fractional knapsack: sorts items by value/weight ratio. Uses a hard-coded example (W = 50). O(n log n). |
| [firstFit.cpp](lab-final/firstFit.cpp) | First-Fit bin packing: puts each item into the first bin with enough room. Prints the number of bins and the space left in each. O(n · bins). |
| [floyd.cpp](lab-final/floyd.cpp) | Floyd–Warshall on an `n × n` matrix read from input (`1000000000` means no edge). O(n³). |

## Build and run

You need a GCC toolchain, because the programs include `<bits/stdc++.h>`. On macOS, install GCC with Homebrew and use `g++-<version>`, since Apple clang does not ship this header.

```bash
g++ -std=c++17 -O2 lab-06/dijkstra.cpp -o dijkstra
./dijkstra < input.txt
```

`lab-03/balance_three_stacks_maxSum.cpp` includes a local debug header (`deBUG.h`, not tracked) unless `ONLINE_JUDGE` is defined, so compile it with:

```bash
g++ -std=c++17 -O2 -DONLINE_JUDGE lab-03/balance_three_stacks_maxSum.cpp -o balance
```

Some files end with a commented sample input, for example `lab-06/dijkstra.cpp`.

## Known limitations

These are lab submissions, kept as they were written:

- `lab-06/dijkstra.cpp` and `lab-07/dijkstra.cpp` read `n` edge lines rather than `m`, so the input needs as many edges as nodes.
- `lab-08/bellman_ford.cpp` starts distances at `INT_MAX` and does not skip unreachable nodes before relaxing, so `INT_MAX + w` can overflow.
- `lab-13/four_queen_problem.cpp` is unfinished (see above).

## Author

Ratul Hasan · [ratulhasan.dev](https://ratulhasan.dev)
