# Binary Search: A Comprehensive Guide

## Table of Contents
1. [Introduction](#introduction)
2. [Key Concepts](#key-concepts)
3. [How It Works](#how-it-works)
4. [Pros and Cons](#pros-and-cons)
5. [C++ Examples](#C++-examples)
    - [Example 1: Binary Search in an Array](#example-1-linear-search-in-an-array)
    - [Example 2: Binary Search in a List of Strings](#example-2-linear-search-in-a-list-of-strings)
    - [Example 3: Binary Search in a Linked List](#example-3-linear-search-in-a-linked-list)
6. [Summary](#summary)

## Introduction

Binary search is a highly efficient algorithm for finding an element in a sorted list. It works by repeatedly dividing the search interval in half. If the value of the search key is less than the item in the middle of the interval, narrow the interval to the lower half. Otherwise, narrow it to the upper half. Repeat until the value is found or the interval is empty.
## Key Concepts

1. **Definition**: Binary search finds the position of a target value within a sorted array. The algorithm compares the target value to the middle element of the array. If they are not equal, the half in which the target cannot lie is eliminated and the search continues on the remaining half until it is successful or the remaining half is empty.
2. **Time Complexity**: 
   - **Best Case**: \(O(1)\) - when the target element is the middle element..
   - **Average Case**: \(O(log(n))\) - where n is the number of elements in the list.
   - **Worst Case**: \(O(log(n))\) - when the element is not present, requiring log(n) comparisons..
3. **Space Complexity**:
   - Iterative \(O(1)\) - requires a constant amount of additional space.
   - Recursive \(O(log(n))\) - requires space proportional to the depth of the recursion tree.
   
4. **Applicability**: Binary search is applicable to any data structure that supports random access and is sorted. The most common use cases are with arrays and vectors.
## How It Works

1. Start with the middle element of the array.
2. If the target element is equal to the middle element, return the index of the middle element.
3. If the target element is smaller than the middle element, repeat the search on the left subarray.
4. If the target element is larger than the middle element, repeat the search on the right subarray.
5. Repeat steps 2-4 until the element is found or the subarray is empty.
## Pros and Cons

**Pros:**
- Much faster than linear search for large datasets.
- Time complexity is logarithmic, which is very efficient.

**Cons:**
- Requires the collection to be sorted.
- More complex to implement than linear search.

## C++ Examples

### Example 1: Binary Search in an Array

```cpp
#include <iostream>
int BinarySearch(int arr[],int n,int x){
int left=0;
int right=n-1;
    while(left<=right){
        ll mid=(left+right)/2;
        if(arr[mid]==x)return mid;
        else if(arr[mid]>x){
            right=mid-1;
        }else left=mid+1;
    }
    return -1;
}

int main() {
    int arr[] = {2, 3, 4, 10, 40};
    int n = sizeof(arr) / sizeof(arr[0]);
    int target = 10;
    int result = binarySearch(arr, n, target);

    if (result != -1) {
        std::cout << "Element found at index: " << result << std::endl;
    } else {
        std::cout << "Element not found in the array." << std::endl;
    }

    return 0;
}


```
#### Output:
```markdown
Element found at index: 3
```

### Example 2: Binary Search in a List of Strings
```cpp
#include <iostream>

int BinarySearch(int arr[],int n,int x){
int left=0;
int right=n-1;
    while(left<=right){
        ll mid=(left+right)/2;
        if(arr[mid]==x)return mid;
        else if(arr[mid]>x){
            right=mid-1;
        }else left=mid+1;
    }
    return -1;
}
int main() {
    std::vector<std::string> vec = {"apple", "banana", "cherry", "date", "fig"};
    std::string target = "cherry";

    // Ensure the vector is sorted (important for binary search)
    std::sort(vec.begin(), vec.end());

    int result = binarySearch(vec, target);

    if (result != -1) {
        std::cout << "Element found at index: " << result << std::endl;
    } else {
        std::cout << "Element not found in the vector." << std::endl;
    }

    return 0;
}

```
#### Output:
```markdown
Element found at index: 2
```

### Example 3: Binary Search in a Linked List
```cpp
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

Node* newNode(int x)
{
    struct Node* temp = new Node;
    temp->data = x;
    temp->next = NULL;
    return temp;
}

// function to find out middle element
struct Node* middle(Node* start, Node* last)
{
    if (start == NULL)
        return NULL;

    struct Node* slow = start;
    struct Node* fast = start->next;

    while (fast != last) {
        fast = fast->next;
        if (fast != last) {
            slow = slow->next;
            fast = fast->next;
        }
    }

    return slow;
}

// Function for implementing the Binary
// Search on linked list
struct Node* binarySearch(Node* head, int value)
{
    struct Node* start = head;
    struct Node* last = NULL;

    do {
        // Find middle
        Node* mid = middle(start, last);

        // If middle is empty
        if (mid == NULL)
            return NULL;

        // If value is present at middle
        if (mid->data == value)
            return mid;

        // If value is more than mid
        else if (mid->data < value)
            start = mid->next;

        // If the value is less than mid.
        else
            last = mid;

    } while (last == NULL || last != start);

    // value not present
    return NULL;
}

// Driver Code
int main()
{
    Node* head = newNode(1);
    head->next = newNode(4);
    head->next->next = newNode(7);
    head->next->next->next = newNode(8);
    head->next->next->next->next = newNode(9);
    head->next->next->next->next->next = newNode(10);
    int value = 7;
    if (binarySearch(head, value) == NULL)
        printf("Value not present\n");
    else
        printf("Present");
    return 0;
}
```
#### Output:
```markdown
Present
```

## Summary
Binary search is a powerful and efficient search algorithm for finding elements in a sorted list. Its logarithmic time complexity makes it much faster than linear search for large datasets. However, it requires the dataset to be sorted and can be more complex to implement. Despite these limitations, its efficiency makes it an invaluable tool in computer science and programming.
