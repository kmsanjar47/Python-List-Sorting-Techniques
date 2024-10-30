# Python List Sorting Techniques

Welcome to the **Python List Sorting Techniques** repository! This README introduces various ways to sort lists in Python using both built-in functions and classic sorting algorithms. Sorting is a fundamental operation in data manipulation, used frequently in data science, software development, and algorithmic programming.

## Contents

1. [Introduction](#introduction)
2. [Python's Built-in Sort Methods](#pythons-built-in-sort-methods)
3. [Bubble Sort](#bubble-sort)
4. [Selection Sort](#selection-sort)
5. [Insertion Sort](#insertion-sort)
6. [Merge Sort](#merge-sort)
7. [Quick Sort](#quick-sort)
8. [Conclusion](#conclusion)

---

## Introduction

Sorting is an essential technique for arranging data in a specific order. Whether it's ascending or descending, sorting is crucial in applications that require efficient data organization and retrieval. This article covers a range of sorting techniques in Python, from built-in functions to popular algorithms.

---

## Python's Built-in Sort Methods

Python provides two built-in methods for sorting: `sorted()` and `.sort()`. The `sorted()` function returns a new sorted list, while the `.sort()` method sorts the list in place.

### Code Example

```python
# Using sorted()
numbers = [5, 2, 9, 1, 5, 6]
sorted_numbers = sorted(numbers)
print("Sorted list:", sorted_numbers)

# Using .sort() in-place
numbers.sort()
print("In-place sorted list:", numbers)
```
---
## Bubble Sort
Bubble Sort is a simple sorting algorithm that repeatedly steps through the list, compares adjacent elements, and swaps them if they are in the wrong order. It's not the most efficient but is easy to understand.
### Code Example
```python
def bubble_sort(arr):
    n = len(arr)
    for i in range(n):
        for j in range(0, n-i-1):
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]

# Example Usage
numbers = [5, 2, 9, 1, 5, 6]
bubble_sort(numbers)
print("Bubble sorted list:", numbers)
```
---
---
## Selection Sort
Selection Sort repeatedly finds the minimum element from the unsorted portion of the list and moves it to the sorted portion. This algorithm is more efficient than Bubble Sort but still not optimal for large lists.
### Code Example
```python
def selection_sort(arr):
    n = len(arr)
    for i in range(n):
        min_idx = i
        for j in range(i+1, n):
            if arr[j] < arr[min_idx]:
                min_idx = j
        arr[i], arr[min_idx] = arr[min_idx], arr[i]

# Example Usage
numbers = [5, 2, 9, 1, 5, 6]
selection_sort(numbers)
print("Selection sorted list:", numbers)
```
---

---
## Insertion Sort
Insertion Sort builds a sorted portion of the list one element at a time by repeatedly picking the next element and inserting it into the correct position within the sorted portion. It's efficient for small or nearly sorted lists.
### Code Example
```python
def insertion_sort(arr):
    for i in range(1, len(arr)):
        key = arr[i]
        j = i - 1
        while j >= 0 and key < arr[j]:
            arr[j + 1] = arr[j]
            j -= 1
        arr[j + 1] = key

# Example Usage
numbers = [5, 2, 9, 1, 5, 6]
insertion_sort(numbers)
print("Insertion sorted list:", numbers)
```
---

---
## Merge Sort
Merge Sort is a divide-and-conquer algorithm that divides the list into halves, recursively sorts each half, and merges the sorted halves back together. It has a time complexity of 𝑂(𝑛log𝑛)O(nlogn), making it efficient for larger lists.
### Code Example
```python
def merge_sort(arr):
    if len(arr) > 1:
        mid = len(arr) // 2
        left = arr[:mid]
        right = arr[mid:]

        merge_sort(left)
        merge_sort(right)

        i = j = k = 0
        while i < len(left) and j < len(right):
            if left[i] < right[j]:
                arr[k] = left[i]
                i += 1
            else:
                arr[k] = right[j]
                j += 1
            k += 1

        while i < len(left):
            arr[k] = left[i]
            i += 1
            k += 1

        while j < len(right):
            arr[k] = right[j]
            j += 1
            k += 1

# Example Usage
numbers = [5, 2, 9, 1, 5, 6]
merge_sort(numbers)
print("Merge sorted list:", numbers)
```
---
---
## Quick Sort
Quick Sort is another divide-and-conquer algorithm that selects a "pivot" element and partitions the list around it, placing smaller elements to the left and larger elements to the right. It is efficient with a time complexity of 𝑂(𝑛log𝑛) on average.

### Code Example
```python
def quick_sort(arr):
    if len(arr) <= 1:
        return arr
    pivot = arr[len(arr) // 2]
    left = [x for x in arr if x < pivot]
    middle = [x for x in arr if x == pivot]
    right = [x for x in arr if x > pivot]
    return quick_sort(left) + middle + quick_sort(right)

# Example Usage
numbers = [5, 2, 9, 1, 5, 6]
sorted_numbers = quick_sort(numbers)
print("Quick sorted list:", sorted_numbers)
```
---
---
## Conclusion
Each sorting technique has its strengths and weaknesses. Python’s built-in methods are generally the fastest, but learning about sorting algorithms helps deepen your understanding of algorithmic complexity and efficiency. Experiment with these examples to find the best method for your data needs!
---
