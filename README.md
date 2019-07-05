# Decision Trees & Cross Validation

## Project Objective:

The purpose of this project is to predict whether the student will pay for the MOOC course. The variables chosen for the decision (classification) tree are A student's average grade for the course exam and for course assignments. The original tree was compared to the pruned tree to prevent the "overfitting" problem based on the error rates of both trees.

## Datasets:

  * MOOC1.csv
  * MOOC2.csv
  
In this project, data from a MOOC will be examined. It contains the following per-student variables:

certified (yes/no) - Whether or not a student paid for the course  
forum.posts (numeric) - How many forum posts a student made throughout the course  
grade (numeric) - A student's average grade for the course exam  
assignment (numeric) - A student's average grade for the course assignments  

## Results:

### Original Tree:

```
c.tree1 <- rpart(certified~grade+assignment, method="class", data=M1)
```
![tree1](https://github.com/lizarova777/assignment6/blob/master/tree1.png)

### Pruned Tree:
```
c.tree2 <- prune(c.tree1, cp = 0.058182)#Set cp to the level at which you want the tree to end
```
![tree2](https://github.com/lizarova777/assignment6/blob/master/tree2.png)

## Intepretation:

The pruned tree seems to have a lower error rate of 46.37% whereas the original tree has a high error rate of 78.14%. As one can see, there is a substantial difference between the error rates of the pruned tree and the original tree. Hence, the original tree is overfitted as opposed to the pruned tree. Thus, the pruned tree is more generalizable. 