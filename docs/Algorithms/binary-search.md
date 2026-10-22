# Binary Search

## 1. Basics of Binary Search

Binary Search is an efficient searching algorithm used to find a target element in a **sorted array**. Instead of checking each element one by one, it repeatedly divides the search interval into two halves.

At each step, the algorithm compares the target value with the middle element:

- If the middle element matches the target, the search is complete.
- If the target is smaller than the middle element, continue searching in the left half.
- If the target is greater than the middle element, continue searching in the right half.

This process continues until the target is found or the search interval becomes empty.

**Important:** Binary Search requires the elements to be sorted. For an ascending array, each comparison allows us to eliminate approximately half of the remaining search space.

### Example

Consider the sorted array:

`[10, 20, 30, 40, 50, 60, 70]`

Suppose we want to find the target value `60`.

1. The middle element is `40`. Since `60 > 40`, search the right half.
2. The middle element of the remaining interval is `60`. The target is found.

Instead of checking every element, Binary Search finds the target in just two comparisons in this example.

## 2. Sample Code (C++)

The following implementation uses an iterative approach to perform Binary Search on a sorted array.

```cpp
#include <iostream>
#include <vector>
using namespace std;

int binarySearch(const vector<int>& arr, int target) {
    int low = 0;
    int high = static_cast<int>(arr.size()) - 1;

    while (low <= high) {
        int mid = low + (high - low) / 2;

        if (arr[mid] == target) {
            return mid;
        } 
        else if (arr[mid] < target) {
            low = mid + 1;
        } 
        else {
            high = mid - 1;
        }
    }

    return -1;
}

int main() {
    vector<int> arr = {10, 20, 30, 40, 50, 60, 70};
    int target = 60;

    int result = binarySearch(arr, target);

    if (result != -1) {
        cout << "Element found at index: " << result << '\n';
    } 
    else {
        cout << "Element not found\n";
    }

    return 0;
}
```

**Output:**

```text
Element found at index: 5
```

### Code Explanation

- `low` represents the first index of the current search interval.
- `high` represents the last index of the current search interval.
- `mid` calculates the middle index without adding `low` and `high` directly, helping avoid integer overflow.
- If `arr[mid]` equals the target, the function returns its index.
- If `arr[mid]` is smaller than the target, `low` moves to `mid + 1`.
- If `arr[mid]` is greater than the target, `high` moves to `mid - 1`.
- If the loop ends without finding the target, the function returns `-1`.

## 3. Time Complexity

Binary Search eliminates approximately half of the remaining search elements in every iteration. Therefore, the number of iterations grows logarithmically with the size of the array.

| Case | Time Complexity | Explanation |
|---|---|---|
| Best Case | \(O(1)\) | The target is the middle element in the first comparison. |
| Average Case | \(O(\log n)\) | The search interval is repeatedly divided in half. |
| Worst Case | \(O(\log n)\) | The algorithm continues until the target is found or the interval becomes empty. |

Here, \(n\) represents the number of elements in the array.

For example, an array containing 1,024 elements requires at most about 11 comparisons in the worst case for this implementation.

## 4. Space Complexity

The iterative implementation uses a constant amount of additional memory. It only maintains a few variables, such as `low`, `high`, `mid`, and `target`.

Therefore, its **auxiliary space complexity is \(O(1)\)**.

The algorithm does not create another array or use additional data structures proportional to the input size.

**Note:** A recursive implementation of Binary Search typically requires \(O(\log n)\) auxiliary space because of the function call stack.