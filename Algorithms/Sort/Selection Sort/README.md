## Introduction
Selection sort is a simple and intuitive sorting algorithm. It works by dividing the array into a sorted and an unsorted region, then repeatedly selecting the smallest (or largest, depending on the order) element from the unsorted region and moving it to the end of the sorted region. This process continues until the entire array is sorted.

## How Selection Sort Works
1. Initialize the first position as the minimum.
2. Find the minimum element in the unsorted part of the array.
3. Swap the found minimum element with the first position of the unsorted part.
4. Move the boundary of the sorted part one position to the right.
5. Repeat the process until the entire array is sorted.

## Time Complexity
### Best case: 
𝑂(𝑛2)
### Average case: 
𝑂(𝑛2)
### Worst case: 
𝑂(𝑛2)

## Space Complexity: 
𝑂(1)
O(1) (in-place sorting)

## C++ Implementation

```cpp
#include <iostream>
#include <vector>

// Function to find the index of the smallest element in the array
int findSmallest(const std::vector<int>& arr) {
    int smallest = arr[0];  // Stores the smallest value
    int smallest_index = 0; // Stores the index of the smallest value
    for (int i = 1; i < arr.size(); ++i) {
        if (arr[i] < smallest) {
            smallest = arr[i];
            smallest_index = i;
        }
    }
    return smallest_index;
}

// Function to sort the array using selection sort algorithm
vector<int> selectionSort(std::vector<int> arr) {
    vector<int> newArr;
    int n = arr.size();
    for (int i = 0; i < n; ++i) {
        int smallest = findSmallest(arr);
        newArr.push_back(arr[smallest]);
        arr.erase(arr.begin() + smallest);
    }
    return newArr;
}

int main() {
    vector<int> arr = {5, 3, 6, 2, 10};
    vector<int> sortedArr = selectionSort(arr);
    for (int num : sortedArr) {
        cout << num << " ";
    }
    cout << std::endl;
    return 0;
}

```

### Expected Output:

``` markdown 
2 3 5 6 10
```
## Conclusion
Selection sort is an educational algorithm suitable for small datasets or when simplicity is more critical than performance. Despite its inefficiencies, understanding selection sort helps build a foundational understanding of sorting algorithms.
