# Ex.No: 3  Implementation of Minimax Search
### DATE:                                                                            
### REGISTER NUMBER : 212221040160
### AIM: 
Write a mini-max search algorithm to find the optimal value of MAX Player from the given graph.
### Algorithm:
1. Start the program
2. import the math package
3. Specify the score value of leaf nodes and find the depth of binary tree from leaf nodes.
4. Define the minimax function
5. If maximum depth is reached then get the score value of leaf node.
6. Max player find the maximum value by calling the minmax function recursively.
7. Min player find the minimum value by calling the minmax function recursively.
8. Call the minimax function  and print the optimum value of Max player.
9. Stop the program. 

### Program:
```
import math
def minimax (curDepth, nodeIndex,maxTurn, scores,targetDepth):
 # base case : targetDepth reached
 if (curDepth == targetDepth):
     return scores[nodeIndex]
 if (maxTurn):
     return max(minimax(curDepth + 1, nodeIndex * 2,False, scores, targetDepth),minimax(curDepth + 1, nodeIndex * 2 + 1,False, scores, targetDepth))
 else:
     return min(minimax(curDepth + 1, nodeIndex * 2,True, scores, targetDepth),minimax(curDepth + 1, nodeIndex * 2 + 1,True, scores, targetDepth))
# Driver code
scores = [3, 5, 2, 9, 12, 5, 23, 20]
treeDepth = math.log(len(scores), 2) # calculate depth of node log 8 (base 2) = 3)
print("The optimal value is : ", end = "")
print(minimax(0, 0, True, scores, treeDepth)) 
```

### Output:
![Screenshot 2023-10-18 085703](https://github.com/hariharan2383/AI_Lab_2023-24/assets/117346668/44b50042-54b4-466b-931c-9a9a34b3b79d)



### Result:
Thus the optimum value of max player was found using minimax search.
