# Algorithm 1: Bubble Sort
#
# Bubble Sort does several 'passes' through a list.
# In each pass, it proceeds element-by-element through the list.
# At each step in the pass, it compares adjacent elements and swaps them if they are in the wrong order.
# The passes continue until the list is sorted.



def bubble_sort(arr):
    for i in range(len(arr)):
        for j in range((len(arr) - 1)):
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]
    return arr
#print(bubble_sort([4,5,6,3,2,1]))

# Algorithm 2: Selection Sort
#
# Selection Sort divides the input list into two parts: the sublist of sorted items on the left and the sublist of unsorted items on the right,
# Initially, the sorted sublist is empty and the unsorted sublist is the entire input list.
# This algorithm also does a series of passes through the unsorted portion of the list.
# In each pass, it finds the smallest element in the unsorted sublist and swaps it with the leftmost unsorted element.
# The leftmost element in the unsorted list is now the greatest element in the sorted sublist.
# The sorted sublist grows by one element each time and the unsorted sublist shrinks by one element each time.
# This process continues until the entire list is sorted and the unsorted list is empty.


def selection_sort(arr):
    for i in range(len(arr)-1):
        smallest = arr[i]
        index = i
        for j in range(i, len(arr)):
            if (arr[j] <= smallest):
                smallest = arr[j]
                index = j
        arr[i], arr[index] = smallest, arr[i]
        
    return arr
#print(selection_sort([3,5,2,6,1,0]))

# n + (n-1) + ... + 2 + 1 = n(n+1)/2 ~ O(n^2)

# smallest: 0

# Algorithm 3: Insertion Sort
#
# Insertion Sort is a simple sorting algorithm that builds the final sorted array (or list) one item at a time.
# Like selection sort, it divides the input list into two parts: the sorted sublist on the left and the unsorted sublist on the right.
# It takes the first element of the unsorted sublist, and inserts it into the sorted sublist.
# If it needs to be inserted in the middle of the sorted sublist, it will have to shift all the following elements to the right. 
# Unlike selection sort, it takes the first unsorted element, instead of doing a pass to find the minimum.


def insertion_sort(arr):
    for i in range(1, len(arr)):
        sorted = arr[i]
        j = i - 1
        while(sorted < arr[j] and j >= 0):
            arr[j+1] = arr[j]
            j -= 1
        arr[j+1] = sorted
        
    return arr
    
#print(insertion_sort([8,3,2,7,4]))

# Algorith 4: Merge Sort
#
# Implement the Merge Sort algorithm.
# Merge Sort is a Divide and Conquer algorithm. 
# It divides the input array into two halves, and recursively calls itself on the two halves,
# The algorithm then merges the two sorted halves to produce the final sorted array.


# [1, 3, 4, 6, 8, 10]
# [0, 1, 2, 5, 5, 7]

def merge_sort(arr):
    if (len(arr) ==1):
        return arr
    else:
        mid = len(arr) // 2
        left = arr[:mid]
        right = arr[mid:]
        
        left_sort = merge_sort(left)
        right_sort = merge_sort(right)
        
        sorted = []
        i = 0
        j = 0
        
        while (i < len(left_sort) and j < len(right_sort)):
            if (left_sort[i] < right_sort[j]):
                sorted.append(left_sort[i])
                i += 1
            else:
                sorted.append(right_sort[j])
                j += 1
        #add rest of list from where you left off
        sorted.extend(left_sort[i:])
        sorted.extend(right_sort[j:])
        return sorted


def merge_sort_alt(arr):
    if (len(arr) ==1):
        return arr
    else:
        mid = len(arr) // 2
        left = arr[:mid]
        right = arr[mid:]

        left_sort = merge_sort(left)
        right_sort = merge_sort(right)

        sorted = []

        while left_sort and right_sort:
            if (left_sort[0] < right_sort[0]):
                sorted.append(left_sort.pop(0))
            else:
                sorted.append(right_sort.pop(0))

        sorted.extend(left_sort)
        sorted.extend(right_sort)
        return sorted

#print(merge_sort([1,6,3,4,2,1]))

# Algorithm 5: Quick Sort
#
# Quick Sort is another Divide and Conquer algorithm.
# It picks an element as pivot and partitions the given array around the picked pivot.
# There are many different versio ns of quickSort that pick pivot in different ways.
# After partitioning, it recursively sorts the subarrays on each side of the pivot.


def quick_sort(arr):
    if (len(arr) == 1):
        return arr
    else:
        pivot = arr[len(arr) - 1]
        left = []
        right = []
        mid = []
        
        for num in arr:
            if (num < pivot):
                left.append(num)
            elif (num == pivot):
                mid.append(num)
            else:
                right.append(num)
                
        print(f"left: {left}")
        print(f"mid: {mid}")
        print(f"right: {right}")
        
        left_sorted = quick_sort(left)
        right_sorted = quick_sort(right)

        return left_sorted + mid + right_sorted
        
#print(quick_sort([2,1,5,2,3,4]))


# Algorithm 6: Counting Sort
#
# Counting Sort is an integer sorting algorithm.
# It is good for sorting elements that have a small number of possible values.
# It starts by creating a size k 'counts' array of zeros, where k is the range of input values ((max - min) + 1).
# For each value in the input array, it increments the corresponding 'counts' array element by 1.
# Once completed, it uses the 'count' array to create the sorted output array.
# It does so by decrementing the counts array by 1 and placing the corresponding input value into the output array.

def counting_sort(arr):
    # arr contains only integers >=0
    counts = []
    sorted = []

    arr_min = min(arr)
    arr_max = max(arr)
    
    for i in range(arr_max - arr_min + 1):
        counts.append(0)

    for num in arr:
        # num - min = idx
        # num = idx + min
        counts[num - arr_min] += 1

    # idx1 -> count
    # idx2 -> sorted
    # idx1 != idx2

    for j in range(len(counts)):
        idx = j
        while (counts[j] > 0):
            sorted.append(idx + arr_min)
            j -= 1
    return sorted

print(counting_sort([2,3,5,2,3]))
