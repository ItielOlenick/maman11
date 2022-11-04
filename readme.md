# Search problems
## Q1 - Q4
As all of these different search algorithms are essentially the same and are different only in the frontier
data structure, I wrote a generic method that is in use by all of these search algorithms.
If there is no heuristic we will use the null heuristic by default.

* In the depthFirstSearch the frontier is a stack
* In the breadthFirstSearch the frontier is a queue
* In the uniformCostSearch the frontier is a PriorityQueueWithFunction where the function is plainly the cost
* In aStarSearch the frontier is a PriorityQueueWithFunction where the function is the cost plus the calculated heuristic
for the node.

## Q5
In order to find all corners we start by having a tuple of corners left to visit.
We need to modify the getSuccessors function so that we explore the 4 direction. If there is no wall, we pass the corners
left minus the successors location if the successor is a corner (using the difference operator).
We reach the goalState when we visited all corners - the tuple holding the corners left is empty.

## Q6
The heuristic used is the max value of the Manhattan distances between pacman and the corners left (defined in Q5) to visit.
This heuristic is admissible since it is equal to or less than the steps needed to be taken since it does not
take walls into consideration.

## Q7
The heuristic used is the max maze distance between pacman's current location and a piece of food. it is admissible as we
know that pacman will need to visit those location one way or another, and this IS the shortest path.
We are 'caching' these values every time we calculate them in order to save calculation time.

## Q8
After adding the gaol state to isGoalState I've used the BFS algorithm from Q2 and got the needed result. 