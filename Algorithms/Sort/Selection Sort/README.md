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
Copy code
#include <iostream>
#include <vector>
#include <algorithm> // For std::swap

void selection_sort(std::vector<int>& arr) {
    int n = arr.size();
    for (int i = 0; i < n - 1; ++i) {
        // Find the minimum element in the remaining unsorted array
        int min_index = i;
        for (int j = i + 1; j < n; ++j) {
            if (arr[j] < arr[min_index]) {
                min_index = j;
            }
        }
        // Swap the found minimum element with the first element of the unsorted array
        std::swap(arr[i], arr[min_index]);
    }
}

int main() {
    std::vector<int> arr = {64, 25, 12, 22, 11};
    selection_sort(arr);
    std::cout << "Sorted array is: ";
    for (int num : arr) {
        std::cout << num << " ";
    }
    std::cout << std::endl;
    // Output: Sorted array is: 11 12 22 25 64
    return 0;
}
```

### Expected Output:

``` markdown 
Sorted array is: 11 12 22 25 64
```
## Conclusion
Selection sort is an educational algorithm suitable for small datasets or when simplicity is more critical than performance. Despite its inefficiencies, understanding selection sort helps build a foundational understanding of sorting algorithms.
