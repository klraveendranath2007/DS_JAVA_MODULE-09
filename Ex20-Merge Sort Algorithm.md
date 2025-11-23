# Ex20 Sorting an Array using Merge Sort Algorithm
## DATE:23-10-2025
## AIM:
To design a program that sorts a given array of integers in ascending order without using built-in sorting functions, achieving O(n log n) time complexity and minimal space usage.
## Algorithm
1. Start the program.  
2. Divide the array into two halves using recursion.  
3. Continue dividing until each subarray contains a single element.  
4. Merge the subarrays in sorted order using a helper merge function.  
5. Return the fully sorted array.  
6. Display the sorted arra   

## Program:
```java
/*
Program to sorts a given array of integers in ascending order without using built-in sorting functions
Developed by: K L RAVEENDRANATH
RegisterNumber:  212224060212
*/

import java.util.*;
public class Solution {
    
    private void swap(int[] arr, int index1, int index2) {
        int temp = arr[index1];
        arr[index1] = arr[index2];
        arr[index2] = temp;
    }

    // Heapify the subtree rooted at index i
    private void heapify(int[] arr, int n, int i) {
        int largest = i; 
        int left = 2 * i + 1;
        int right = 2 * i + 2; 

        if (left < n && arr[left] > arr[largest]) {
            largest = left;
        }

        if (right < n && arr[right] > arr[largest]) {
            largest = right;
        }

        if (largest != i) {
            swap(arr, i, largest); 
            heapify(arr, n, largest);
        }
    }

    private void heapSort(int[] arr) {
        int n = arr.length;
        for (int i = n / 2 - 1; i >= 0; i--) {
            heapify(arr, n, i);
        }

        for (int i = n - 1; i >= 0; i--) {
            swap(arr, 0, i);
            heapify(arr, i, 0);
        }
    }

    public int[] sortArray(int[] nums) {
        heapSort(nums);
        return nums;
    }

    
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        Solution solution = new Solution();

        //System.out.println("Enter number of elements:");
        int n = sc.nextInt();
        
        int[] nums = new int[n];
        //System.out.println("Enter " + n + " elements:");
        for (int i = 0; i < n; i++) {
            nums[i] = sc.nextInt();
        }

        int[] sorted = solution.sortArray(nums);
        System.out.println("Sorted array:");
        System.out.println(Arrays.toString(sorted));

        sc.close();
    }
}


```

## Output:
<img width="646" height="210" alt="image" src="https://github.com/user-attachments/assets/b059e239-67a3-44a4-984c-6e3381a8003e" />




## Result:
The program has been successfully implemented and executed.
It sorts the given array of integers in ascending order using the Merge Sort algorithm with a time complexity of O(n log n) and minimal extra space.
