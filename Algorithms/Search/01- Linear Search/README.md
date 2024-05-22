# Linear Search: A Comprehensive Guide

## Table of Contents
1. [Introduction](#introduction)
2. [Key Concepts](#key-concepts)
3. [How It Works](#how-it-works)
4. [Pros and Cons](#pros-and-cons)
5. [C++ Examples](#java-examples)
    - [Example 1: Linear Search in an Array](#example-1-linear-search-in-an-array)
    - [Example 2: Linear Search in a List of Strings](#example-2-linear-search-in-a-list-of-strings)
    - [Example 3: Linear Search in a Linked List](#example-3-linear-search-in-a-linked-list)
6. [Summary](#summary)

## Introduction

Linear search, also known as sequential search, is one of the simplest search algorithms. It works by checking each element of a list sequentially until the desired element is found or the list ends.

## Key Concepts

1. **Definition**: Linear search scans each element in a collection one by one until it finds the target value or reaches the end of the collection.
2. **Time Complexity**: 
   - **Best Case**: \(O(1)\) - when the target element is the first element.
   - **Average Case**: \(O(n)\) - where \(n\) is the number of elements in the list.
   - **Worst Case**: \(O(n)\) - when the target element is the last element or not present.
3. **Space Complexity**: \(O(1)\) - requires a constant amount of additional space.
4. **Applicability**: Can be used on any data structure that allows sequential access (arrays, linked lists, etc.).

## How It Works

1. Start from the first element.
2. Compare the current element with the target.
3. If the current element matches the target, return its index.
4. If the current element does not match the target, move to the next element.
5. Repeat steps 2-4 until the element is found or the end of the list is reached.

## Pros and Cons

**Pros:**
- Simple to implement.
- Does not require the collection to be sorted.
- Works well with small datasets.

**Cons:**
- Inefficient for large datasets.
- Time complexity is linear, which can be slow compared to more advanced algorithms like binary search.

## Java Examples

### Example 1: Linear Search in an Array

```cpp
#include <iostream>

int linearSearch(int arr[], int n, int target) {
    for (int i = 0; i < n; ++i) {
        if (arr[i] == target) {
            return i; // Return the index where the target is found
        }
    }
    return -1; // Return -1 if target is not found in the array
}

int main() {
    int arr[] = {5, 3, 8, 4, 2};
    int n = arr.size()
    int target = 2;
    int index = linearSearch(arr, n, target);
    if (index != -1) {
        std::cout << "Element found at index: " << index << std::endl;
    } else {
        std::cout << "Element not found in the array." << std::endl;
    }
    return 0;
}

```
#### Output:
```markdown
Element found at index: 4

```

### Example 2: Linear Search in a List of Strings
```cpp
#include <iostream>
#include <vector>
#include <string>

int linearSearch(const std::vector<std::string>& list, const std::string& target) {
    for (size_t i = 0; i < list.size(); ++i) {
        if (list[i] == target) {
            return i; // Return the index where the target string is found
        }
    }
    return -1; // Return -1 if target string is not found in the list
}

int main() {
    std::vector<std::string> list = {"kiwi", "strawberry", "mango", "grape", "melon"};
    std::string target = "kiwi";
    int index = linearSearch(list, target);
    if (index != -1) {
        std::cout << "Element found at index: " << index << std::endl;
    } else {
        std::cout << "Element not found in the list." << std::endl;
    }
    return 0;
}

```
#### Output:
```markdown
Element found at index: 0
```

### Example 3: Linear Search in a Linked List
```cpp
#include <iostream>
struct Node {
    int data;
    Node* next;
    // Constructor to initialize data and next pointer
    Node(int val) : data(val), next(nullptr) {}
};
Node* linearSearch(Node* head, int target) {
    Node* current = head;
    while (current != nullptr) {
        if (current->data == target) {
            return current; // Return the node where the target is found
        }
        current = current->next;
    }
    return nullptr; // Return nullptr if target is not found in the list
}

int main() {
    Node* head = new Node(3);
    head->next = new Node(7);
    head->next->next = new Node(11);
    head->next->next->next = new Node(15);

    int target = 7;
    Node* result = linearSearch(head, target);

    if (result != nullptr) {
        std::cout << "Element " << target << " found in the linked list." << std::endl;
    } else {
        std::cout << "Element " << target << " not found in the linked list." << std::endl;
    }
    return 0;
}

```
#### Output:
```markdown
Element 7 found in the linked list.
```

## Summary
Linear search is a straightforward and easy-to-understand algorithm that is useful for small datasets and unsorted collections. While it may not be the most efficient for larger datasets, its simplicity makes it a good starting point for learning search algorithms.
