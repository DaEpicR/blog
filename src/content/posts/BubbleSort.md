---
title: BubbleSort Algorithm Explained
description: Explaining BubbleSort Algorithm in a simple way
publishedDate: 2024-07-21
tags:
  - programming
  - Guide
---

## Bubble Sort Algorithm Explained

Bubble sort is a simple sorting algorithm that repeatedly steps through the list, compares adjacent elements, and swaps them if they are in the wrong order. It is named for the way smaller or larger elements "bubble" to the top of the list with each pass.

### Implementation in Python

#### Single Pass Example

```python
def bubble_sort_single_pass(data):
    """
    Perform a single pass of bubble sort on the list `data`.
    """
    for i in range(len(data) - 1):
        if data[i] > data[i + 1]:
            # Swap elements if they are in the wrong order
            data[i], data[i + 1] = data[i + 1], data[i]

    return data
```

#### Multiple Passes Example

```python
def bubble_sort_multiple_passes(data):
    """
    Perform bubble sort on the list `data` with multiple passes.
    """
    n = len(data)
    for i in range(n - 1):
        # Last i elements are already sorted, so no need to check them
        for j in range(0, n - i - 1):
            if data[j] > data[j + 1]:
                # Swap elements if they are in the wrong order
                data[j], data[j + 1] = data[j + 1], data[j]

    return data
```

### Visual Representation

#### Initial List: `[5, 3, 8, 2, 7]`

#### Single Pass Visualization

- **Before Pass**:

  ```python
  [5, 3, 8, 2, 7]
  ```

- **After Single Pass**:
  ```python
  [3, 5, 8, 2, 7]   (after swapping 5 and 3)
  ```

#### Multiple Passes Visualization

- **Pass 1**:

  ```python
  [3, 5, 8, 2, 7]   (after pass 1)
  [3, 5, 2, 7, 8]   (after pass 2)
  [3, 2, 5, 7, 8]   (after pass 3)
  [2, 3, 5, 7, 8]   (after pass 4)
  ```

- **Final Sorted List**:
  ```python
  [2, 3, 5, 7, 8]
  ```

### Conclusion

Bubble sort is straightforward to implement and understand but may not be efficient for large datasets due to its $O(n^2)$ time complexity. It repeatedly passes through the list, swapping adjacent elements until the list is sorted. The algorithm is useful for educational purposes and small datasets where simplicity is prioritized over speed.
