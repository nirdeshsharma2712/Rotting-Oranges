# 📊 LeetCode Problem: Rotting Oranges

## 🧩 Problem Statement

You are given an `m x n` grid where each cell can have one of **three values**:
- `0` representing an **empty cell**,
- `1` representing a **fresh orange**, or
- `2` representing a **rotten orange**.
  
Return the **minimum** number of minutes that must elapse until no cell has a **fresh orange**. If this is impossible, `return -1`.

> **Note :**
> - Every minute, any fresh orange that is 4-directionally adjacent to a rotten orange becomes rotten.



## 🧠 Approach: BFS (Breadth-First Search)

- Traverse the **grid** and **push** all **rotten oranges** into a **queue**.

- At the same time, `count` **fresh oranges**.

- Use **BFS traversal**: each level of **BFS** represents `1` minute.

- For every **rotten orange**, spread rot to its `4-directional neighbors`.

- Update **grid** and **decrease** fresh count.

- Keep **track** of time (minutes).

- If after **BFS**, no **fresh oranges** remain, return the **total minutes**.

- Else, `return -1`.



## ✅ Example Walkthrough

### Example 1

##### Input: grid = [[2,1,1],[1,1,0],[0,1,1]]
##### Output: 4


### Example 2

##### Input: grid = [[2,1,1],[0,1,1],[1,0,1]]
##### Output: -1

##### Explanation: 
<pre> 
 - The orange in the bottom left corner (row 2, column 0) is never rotten, because rotting only happens 4-directionally.
  
</pre>

### Example 3

##### Input: grid = [[0,2]]
##### Output: 0

##### Explanation: 
<pre> 
  - Since there are already no fresh oranges at minute 0, the answer is just 0.
  
</pre>

## 🛠️ Constraints

- `m == grid.length`
- `n == grid[i].length`
- `1 <= m, n <= 10`
- `grid[i][j]` is `0`, `1`, or `2`.
