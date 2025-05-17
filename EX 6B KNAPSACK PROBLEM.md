# EX 6B KNAPSACK PROBLEM  
## DATE:  
*Enter the date here*  

## AIM:  
To demonstrate a Python program using dynamic programming for the 0/1 knapsack problem.  

## Algorithm  
1. Start with inputs for the number of items, their weights and values, and the knapsack capacity.  
2. Define a recursive function `knapSack(W, wt, val, n)` to calculate maximum value.  
3. Use base conditions: if `n == 0` or `W == 0`, return 0.  
4. If the weight of the nth item is more than the capacity `W`, exclude it.  
5. Otherwise, consider the maximum of two cases:  
   - nth item included  
   - nth item not included  
6. Return the result of the recursive function.  

## Program:
```python
# To implement the program for 0/1 Knapsack problem.

# Developed by: Sandhya B N
# Register Number: 212222040144

def knapSack(W, wt, val, n):
    # Base Condition
    if n == 0 or W == 0:
        return 0
    # If weight of the nth item is more than Knapsack capacity W, then exclude the item
    if wt[n-1] > W:
        return knapSack(W, wt, val, n-1)
    # Return the maximum of including or not including the nth item
    return max(val[n-1] + knapSack(W - wt[n-1], wt, val, n-1), knapSack(W, wt, val, n-1))

# Input section
x = int(input("Enter number of values: "))
y = int(input("Enter number of weights: "))
W = int(input("Enter the capacity of the knapsack: "))

val = []
wt = []

print("Enter the values:")
for i in range(x):
    val.append(int(input()))

print("Enter the weights:")
for j in range(y):
    wt.append(int(input()))

n = len(val)
print('The maximum value that can be put in a knapsack of capacity', W, 'is:', knapSack(W, wt, val, n))
```
## OUTPUT
<img width="713" alt="image" src="https://github.com/user-attachments/assets/aeb8ff84-a51c-4156-a452-c6cdb8f682d0" />

## Result:
Thus the program was executed successfully for finding the maximum value that can be put in a knap sack of capacity .
