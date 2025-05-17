
# EX 6A CHERRY PICK UP PROBLEM  
## DATE:  
## AIM:  
To Create a Python program for the following problem statement.  
You are given an n x n grid representing a field of cherries, each cell is one of three possible integers. 0 means the cell is empty, so you can pass through, 1 means the cell contains a cherry that you can pick up and pass through, or -1 means the cell contains a thorn that blocks your way. Return the maximum number of cherries you can collect by following the rules below: Starting at the position (0, 0) and reaching (n - 1, n - 1) by moving right or down through valid path cells (cells with value 0 or 1). After reaching (n - 1, n - 1), returning to (0, 0) by moving left or up through valid path cells. When passing through a path cell containing a cherry, you pick it up, and the cell becomes an empty cell 0. If there is no valid path between (0, 0) and (n - 1, n - 1), then no cherries can be collected.

## Algorithm:  
1. Define the size of the grid.  
2. Use dynamic programming (DP) to store the maximum cherries collected by two people moving from top to bottom simultaneously.  
3. Initialize a 3D DP table with -infinity.  
4. Traverse through each row and update the possible paths with max cherries by considering movement of both persons.  
5. Return the result from the last row in the DP table.  

## Program:
```
# To implement the program for Cherry Pickup problem.

# Developed by: Sandhya B N
# Register Number: 212222040144

class Solution:
    def cherryPickup(self, grid):
        n = len(grid)
        ### add code here
        dp=[[[-1]*n for _ in range(n)] for _ in range(n)]
        def f(x1,y1,x2):
            y2=x1+y1-x2
            if x1<0 or y1<0 or x2<0 or y2<0 or grid[x1][y1]==-1 or grid[x2][y2]==-1:
                return float('-inf')
            if x1==0 and y1==0 and x2==0 and y2==0:
                return grid[0][0]
            if dp[x1][y1][x2]!=-1:
                return dp[x1][y1][x2]
            cherries=grid[x1][y1]
            if x1!=x2 or y1!=y2:
                cherries+=grid[x2][y2]
            cherries+=max(
                          f(x1-1,y1,x2-1),
                           f(x1,y1-1,x2-1),
                           f(x1-1,y1,x2),
                           f(x1,y1-1,x2))
            dp[x1][y1][x2]=cherries
            return cherries
        result= max(0,f(n-1,n-1,n-1))
        return result
obj=Solution()
grid=[[0,1,-1],[1,0,-1],[1,1,1]]        
print(obj.cherryPickup(grid))
```
## Output:
![image](https://github.com/user-attachments/assets/de7e43da-3cbb-4901-ac25-9f8a1d46dfff)



## Result:
Thus the above program was executed successfully for finding the maximum number of cherries from grid.
