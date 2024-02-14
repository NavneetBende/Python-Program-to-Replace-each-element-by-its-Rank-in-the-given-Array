Replace each element by its Rank in the given Array
In this article, we will learn about Python Program to Replace each element by its Rank in the given Array through the python program. Given an array of distinct integers, we need to replace each element of the array with its rank. The minimum value element will have the highest rank in the Array

Replace each element by its Rank in the given Array
Method Discussed
Method 1 : Using Naive approach.
Method 2 : Using Hash-map.
 

Method 1 :
Create a copy of the given input array.
Sort the copied array.
Run a nested loop and find the position of the given array element in the sorted array.
And replace the element with the position.
Print the modified input array.
Method 1 : Code in Python
def changeArr(input1):
 
    newArray = input1.copy()
    newArray.sort()
     
    for i in range(len(input1)):
        for j in range(len(newArray)):
            if input1[i]==newArray[j]:
                input1[i] = j+1;
                break;
    
# Driver Code
arr = [100, 2, 70, 12 , 90]
changeArr(arr)
# Print the array elements
print(arr)
Output
5 1 3 2 4
Method 2 :
In this method we will use the concept of hashing in replacing the elements of given array by its rank.

Method 2 : Code in Python
def changeArr(input1):
 
    newArray = input1.copy()
    newArray.sort()
    ranks = {}
    rank = 1
     
    for index in range(len(newArray)):
        element = newArray[index];
        if element not in ranks:
            ranks[element] = rank
            rank += 1
         
    for index in range(len(input1)):
        element = input1[index]
        input1[index] = ranks[input1[index]]
 
# Driver Code
arr = [100, 2, 70, 12 , 90]
changeArr(arr)
# Print the array elements
print(arr)
Output
[5, 1, 3, 2, 4]
