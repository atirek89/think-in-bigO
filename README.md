# 📊 Time and Space Complexity

## ⏱️ Time Complexity

Time complexity tells us **how long an algorithm or a set of instructions will take to run**, based on the **size of the input**.

We express time complexity using **Big-O Notation**.

---

### 📊 Common Time Complexities

| Notation   | Name         | Efficiency       | Example                          | Analogy                                                     |
|------------|--------------|------------------|----------------------------------|-------------------------------------------------------------|
| O(1)       | Constant     | Excellent / Best | Accessing the 1st item in a list | Taking the 1st book from a shelf                            |
| O(log n)   | Logarithmic  | Good             | Binary Search                    | Cutting a dictionary in half every time you search          |
| O(n)       | Linear       | Fair             | Looping through a list           | Checking every book one by one                              |
| O(n log n) | Linear-Log   | Bad              | Merge Sort, Heap Sort            | Divide and conquer with a bit more work                     |
| O(n²)      | Quadratic    | Horrible / Worst | Nested loops                     | For every student, ask every other student a question       |
| O(2ⁿ)      | Exponential  | Horrible / Worst | Solving Towers of Hanoi          | Choices double with each input, grows very quickly          |
| O(n!)      | Factorial    | Horrible / Worst | Solving the Traveling Salesman   | Extremely inefficient — tries every possible permutation    |


---

## 💾 Space Complexity

Space complexity measures how much **extra memory** (RAM) an algorithm uses as the input size grows.

- Like time complecity, it's expressed in Big-O.
- It include:
    - Input storage
    - Temporary variables
    - Recursion stack space

### Exampe:
- **Merge Sort** has a time complexity of `O(n log n)` and space complexity of `O(n)` because it uses temporary arrays.
- **Bubble Sort** has a time complexity of `O(n^2)` and space complexity of `O(1)` because it sorts in place.

---

## 🧠 Tip to Remember

> Always aim for **lower time and space complexity**, but balance it with readability and simplicity.  
> A faster algorithm isn't always better if it's too complex to maintain.
