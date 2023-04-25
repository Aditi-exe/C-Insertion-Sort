# Insertion Sort

Insertion sort is a simple sorting algorithm that builds the final sorted array one item at a time. It works by iterating through an array and comparing each element with the elements before it, shifting them up if necessary until the correct position is found for the current element.

The algorithm for insertion sort works as given below:

1. Start with the second element of the array, and compare it with the first element. If the second element is smaller than the first, swap them. Otherwise, leave them as they are.
2. Move to the third element, and compare it with the second element. If the third element is smaller than the second, swap them. Otherwise, compare it with the first element. If the third element is smaller than the first, swap the third element with the first element. Otherwise, leave them as they are.
3. Repeat step 2 for all the remaining elements in the array, until the last element is reached.

The procedure of insertion sort can be represented as follows:

![Representation of insertion sort](https://miro.medium.com/v2/resize:fit:1400/0*1zi2XtjiLXa3LYZh.PNG)

In C, insertion sort can be implemented as follows:

```
void insertionSort(int arr[], int n) {
    int i, key, j;
    for (i = 1; i < n; i++) {
        key = arr[i];
        j = i - 1;

        /* Move elements of arr[0..i-1], that are greater than key, to one position ahead of their current position */
        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j = j - 1;
        }
        arr[j + 1] = key;
    }
}
```

The function above takes an array arr of length n as input and sorts it in ascending order using the insertion sort algorithm. The sorted part and the unsorted part are initially divided in the input array, and the function iterates over the unsorted part one element at a time, inserting it into the correct position in the sorted part by shifting all the elements greater than it one position to the right. The implementation uses a variable key to store the current element that needs to be inserted into the sorted part and a variable j to keep track of the index where it needs to be inserted. The function starts with i = 1 because the first element of the array is already in the sorted part. A while loop is used to shift all the elements greater than key to the right until the correct position for key is found, and key is then inserted into the correct position by setting arr[j + 1] = key.

The program in this repository demonstrates the implementation of insertion sort in C.
