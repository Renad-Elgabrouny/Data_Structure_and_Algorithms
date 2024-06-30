## Quick Sort Algorithm
Quick Sort is a highly efficient sorting algorithm and is based on partitioning of the array of data into smaller arrays. A large array is partitioned into two arrays, one of which holds values smaller than the specified value, say pivot, based on which the partition is made, and another array holds values greater than the pivot value.

## How Quick Sort Works
1. Choose a Pivot: Pick an element from the array as a pivot. This element can be the first element, the last element, the middle element, or any random element.
2. Partitioning: Reorder the array so that all elements with values less than the pivot come before the pivot, while all elements with values greater than the pivot come after it. After this partitioning, the pivot is in its final position.
3. Recursively Apply: Recursively apply the above steps to the sub-array of elements with smaller values and the sub-array of elements with greater values
   

## Quick Sort Implementation in Python
Here's a simple implementation of Quick Sort in Python:

```python

def quicksort(array):
 if len(array) < 2:
 return array 
 else:
 pivot = array[0] 
 less = [i for i in array[1:] if i <= pivot]  
 greater = [i for i in array[1:] if i > pivot] 
 return quicksort(less) + [pivot] + quicksort(greater)

print quicksort([10, 5, 2, 3])
```

## Explanation of the Code

1. Choose a Pivot: Pick an element from the array as a pivot. This element can be the first element, the last element, the middle element, or any random element.
2. Partitioning: Reorder the array so that all elements with values less than the pivot come before the pivot, while all elements with values greater than the pivot come after it. After this partitioning, the pivot is in its final position.
3. Recursively Apply: Recursively apply the above steps to the sub-array of elements with smaller values and the sub-array of elements with greater values.


## Performance
* Average Case: O(n log n)
* Worst Case: O(n^2) (when the smallest or largest element is always chosen as the pivot)
*  Best Case: O(n log n)

Quick Sort is generally faster in practice compared to other O(n log n) algorithms due to better cache performance and fewer data movements.

## Conclusion
* D&C works by breaking a problem down into smaller and smaller pieces.
* If you’re using D&C on a list, the base case is probably an empty array or an array with one element.
* If you’re implementing quicksort, choose a random element as the pivot. The average runtime of quicksort is O(n log n)!
* The constant in Big O notation can matter sometimes. That’s why quicksort is faster than merge sort.
* The constant almost never matters for simple search versus binary search, because O(log n) is so much faster than O(n) when your list gets big.
