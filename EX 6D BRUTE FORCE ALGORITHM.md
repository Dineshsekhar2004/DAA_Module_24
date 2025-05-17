# EX 6D BRUTE FORCE ALGORITHM  
## DATE:  

## AIM:  
To write a Python program using the brute force method for searching a given substring in the main string.

## Algorithm  
1. Read the main string and the substring from the user.  
2. Calculate the lengths of the main string and substring.  
3. Traverse the main string from index 0 to `length(main string) - length(substring) + 1`.  
4. For each index, check if the substring matches the slice of the main string.  
5. If matched, print the index where the substring is found.  

## Program:
```python
# To implement the program using brute force method of searching for the given substring in the main string.

# Developed by: Sandhya B N
# Register Number: 212222040144 

def match(string, sub):
    l = len(string)
    l2 = len(sub)
    for i in range(l - l2 + 1):
        if string[i:i + l2] == sub:
            print("Found at index", i)

str1 = input("Enter the main string: ")
str2 = input("Enter the substring to search: ")
match(str1, str2)
```

## Output:
<img width="585" alt="image" src="https://github.com/user-attachments/assets/6e36112c-c8e3-4873-9c2d-061355914bca" />



## Result:
Thus the above program was executed successfully for searching the substring at respective index.
