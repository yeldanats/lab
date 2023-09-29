1.def selection_sort(alist):
    for i in range(0, len(alist) - 1):
        smallest = i
        for j in range(i + 1, len(alist)):
            if alist[j] < alist[smallest]:
                smallest = j
        alist[i], alist[smallest] = alist[smallest], alist[i]
 
 
alist = input('Enter the list of numbers: ').split()
alist = [int(x) for x in alist]
selection_sort(alist)
print('Sorted list: ', end='')
print(alist)


2.
def insertionSort(array):

    for step in range(1, len(array)):
        key = array[step]
        j = step - 1
        
        # Compare key with each element on the left of it until an element smaller than it is found
        # For descending order, change key<array[j] to key>array[j].        
        while j >= 0 and key < array[j]:
            array[j + 1] = array[j]
            j = j - 1
        
        # Place key at after the element just smaller than it.
        array[j + 1] = key


data = [9, 5, 1, 4, 3]
insertionSort(data)
print('Sorted Array in Ascending Order:')
print(data)


3.def bubble_sort(list1): 
   # We can stop the iteration once the swap has done 
    has_swapped = True 
 
    while(has_swapped): 
        has_swapped = False 
        for i in range(len(list1) - 1): 
            if list1[i] > list1[i+1]: 
                # Swap 
                list1[i], list1[i+1] = list1[i+1], list1[i] 
                has_swapped = True 
    return list1 
 
 
list1 = [5, 3, 8, 6, 7, 2] 
print("The unsorted list is: ", list1) 
# Calling the bubble sort function 
print("The sorted list is: ", bubble_sort(list1)) 
4.
  
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
  

struct Student {
    char* name;
    int id;
    char age;
};
  
// setting up rules for comparison
// to sort the students based on names
int comparator(const void* p, const void* q)
{
    return strcmp(((struct Student*)p)->name,
                  ((struct Student*)q)->name);
}
  

int main()
{
    int i = 0, n = 5;
  
    struct Student arr[n];
  
    // Get the students data
    arr[0].id = 1;
    arr[0].name = "bd";
    arr[0].age = 12;
  
    arr[1].id = 2;
    arr[1].name = "ba";
    arr[1].age = 10;
  
    arr[2].id = 3;
    arr[2].name = "bc";
    arr[2].age = 8;
  
    arr[3].id = 4;
    arr[3].name = "aaz";
    arr[3].age = 9;
  
    arr[4].id = 5;
    arr[4].name = "az";
    arr[4].age = 10;
  
  
    printf("Unsorted Student Records:\n");
    for (i = 0; i < n; i++) {
        printf("Id = %d, Name = %s, Age = %d \n",
               arr[i].id, arr[i].name, arr[i].age);
    }
   
    qsort(arr, n, sizeof(struct Student), comparator);
  

    printf("\n\nStudent Records sorted by Name:\n");
    for (i = 0; i < n; i++) {
        printf("Id = %d, Name = %s, Age = %d \n",
               arr[i].id, arr[i].name, arr[i].age);
    }
  
    return 0;
}

5.
def insertionSort(arr):
 

    for i in range(1, len(arr)):
 
        key = arr[i]
 
   
        j = i-1
        while j >= 0 and key < arr[j] :
                arr[j + 1] = arr[j]
                j -= 1
        arr[j + 1] = key
 
 

arr = [12, 11, 13, 5, 6]
insertionSort(arr)
for i in range(len(arr)):
    print ("% d" % arr[i])
 
6.
def bubbleSort(arr):
    n = len(arr)
     

    for i in range(n):
        swapped = False
 
   
        for j in range(0, n-i-1):
 
            # Traverse the array from 0 to n-i-1
            # Swap if the element found is greater
            # than the next element
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]
                swapped = True
        if (swapped == False):
            break
 

if __name__ == "__main__":
    arr = [64, 34, 25, 12, 22, 11, 90]
 
    bubbleSort(arr)
 
    print("Sorted array:")
    for i in range(len(arr)):
        print("%d" % arr[i], end=" ")
7.
import random
 
def bubble_sort(arr):
    n = len(arr)
    for i in range(n):
        for j in range(n - i - 1):
            if arr[j] > arr[j + 1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
 
def selection_sort(arr):
    n = len(arr)
    for i in range(n):
        min_index = i
        for j in range(i + 1, n):
            if arr[j] < arr[min_index]:
                min_index = j
        arr[i], arr[min_index] = arr[min_index], arr[i]
 
def insertion_sort(arr):
    n = len(arr)
    for i in range(1, n):
        key = arr[i]
        j = i - 1
        while j >= 0 and arr[j] > key:
            arr[j + 1] = arr[j]
            j -= 1
        arr[j + 1] = key

arr = [random.randint(1, 10000) for i in range(10000)]
 

import time
 
start_time = time.time()
bubble_sort(arr.copy())
bubble_sort_time = time.time() - start_time
 
start_time = time.time()
selection_sort(arr.copy())
selection_sort_time = time.time() - start_time
 
start_time = time.time()
insertion_sort(arr.copy())
insertion_sort_time = time.time() - start_time
 
print("Bubble Sort time:", bubble_sort_time)
print("Selection Sort time:", selection_sort_time)
print("Insertion Sort time:", insertion_sort_time)

8.
import re
 
def SortFromExtension(files):

    files.sort(key=lambda s: re.split("\.([^.]+)", s)[1])
 

    print(", ".join(files))
 
if __name__ == "__main__":
    files = ["ajay.cpp", "pchy.pdf", "loki.docx", "raju.zip"]
    SortFromExtension(files
