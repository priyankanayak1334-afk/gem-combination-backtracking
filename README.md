# gem-combination-backtracking
# 💎 Magical Gem Backtracking Search

An interactive implementation of a state-space tree algorithm using **Backtracking** to generate all possible subsets (the Power Set) of magical chest gems. 

## 🎯 Real-World Impact
Backtracking is a foundational computer science strategy. While applied to a magical chest game loop here, this exact algorithmic approach powers:
* **Industrial Scheduling Systems:** Evaluating constraint satisfaction across massive operations.
* **Recommendation Engines:** Traversing option graphs to suggest products.
* **AI Decision Trees:** Generating and evaluation paths in game-playing engines (like Chess or Go).

---

## 🌳 Recursion Decision Tree
Each level of the tree represents a binary decision for a specific gem: either **Include (+)** it or **Exclude (-)** it.

```text
                      [ ] (Empty Chest)
                     /   \
          + Ruby    /     \  - Ruby
                   /       \
             [Ruby]         [ ]
             /    \         /    \
     +Em    /      \ -Em   /      \ +Em
           /        \     /        \
     [Ruby,Em]    [Ruby] [Em]       [ ]
       /   \       /  \   /  \     /   \
  +Sap/     \-Sap /    \ /    \   /     \-Sap
     /       \   /     /       \ /       \
 [R,E,S]   [R,E] [R,S] [R]   [E,S] [E]   [S]   [ ]
```
*Total combinations for \(n\) items = \(2^n\). For 3 items, the algorithm yields exactly **8 combinations**.*

---

## ⚙️ How the Algorithm Works
1. **Incremental Assembly:** The algorithm uses a pointer to walk through the array item by item.
2. **State Forking:** At each item index, the stack splits into two recursive paths: one with the element added, and one without.
3. **Clean Backtracking:** Upon hitting the base case (`index == len(gems)`), the combination is captured. The stack then winds backward, using a `.pop()` operation to reset the state cleanly so alternative branches can be traversed without memory corruption.

---

## 🧪 Verified Test Suite
The implementation includes integrated unit tests utilizing Python's native `unittest` framework to verify:
* ✅ **Empty Input Bounds:** An empty list cleanly evaluates to a single sub-combination `[[]]`.
* ✅ **Single Gem Traversal:** Validates perfect base-split calculations.
* ✅ **Exponential Scale Limits:** Checks combinatorial calculation totals against mathematical counts (\(2^n\)).

---

## 🚀 Running the Project Localy

1. Clone this repository:
   ```bash
   git clone https://github.com
   ```
2. Fire up your Jupyter environment:
   ```bash
   jupyter notebook gem_backtracking.ipynb
   ```
3. Run all code frames to execute the core algorithm and visually watch the test suite pass!
