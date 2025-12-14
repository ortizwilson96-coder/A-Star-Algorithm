# A-Star-Algorithm
Contains a script that implements A* search for a robot to find a goal in a maze
/*
6X6 MAZE SOLVER USING THE A* ALGORITHM

Wilson Ortiz-Lopez
ME 556 Robotic Concepts

*/

//initialization of parameters and structures needed for the 
//algorithm, robot, and maze

//construct contants for the maze parameters

//initaliaze the 2D maze with defined lengths

//initialize the start and end goal coordinates


//variable to hold the heading of the robot. this is needed to perform
//proper selection of cell that is available/not available to the robot
//north = 0, east = 1, south = 2, west = 3

//Creating structure to hold the variables that make up a node in the maze
struct Node {
  //row and column # of each node
  //g(cost to go), h(heuristic or distance to goal), f(the cost to go
  //plus the heuristic)
  
  //the parent node attached to "this" node
  //states if the node is in the open array of nodes
  //states if the node is in the closed for searching
};

//creating instance of Node called nodes 

//initializing an array for the open node locations

//sensor capture functions, created booleans of when each of the sensor
//directions sees a wall
bool wallFront()
{
  //zero(low) means there is a wall
}

bool wallLeft()
{
}

bool wallRight()
{
}

//robot motor movement functions
void forward()
{
  //EN PIN LM
  //PIN1 LM
  //PIN2 LM

  //EN PIN RM
  //PIN4 RM
  //PIN3 RM 
}

void stopMove() 
{
}

void leftTurn()
{
}

void rightTurn()
{
}

void halfSpin()
{
}

//code to align the mouse while moving forward
void straighten() 
{
}

//usefull functions to use within the algorithm...

//a function takes the given row and col and returns an integer
//that equals the location of the maze when it is made into 1-D array
int arrayIndex(int r, int c)
{
}

//a function takes a given row and col and returns true or false
//depending on whether that row and col are within the bounds of the maze
bool bounds(int r, int c)
{
}

//a function that returns true if the node is free or if the node is the goal and returns
//false if the node being checked is outside the bounds of the maze
bool canContinue(int r, int c)
{
}

//this function will provde the correct heading to be implmented in the following
//function for exploration. this will update the next node to explore depending on
//the current heading state of the robot.
void headingDirections(int heading, int dr[4], int dc[4])
{
  //the direction row and columns are adjusted for each cell starting 
  //from the following order: [front], [right], [left], [back]
}

//this function takes in a node that is known to be free and will move the robot in
//the proper direction. this moves the robot to unexplored free spaces in the maze
bool exploreNeighbor(int r, int c, int &r_next, int &c_next)
{
}
 
//mahattan heuristic used to estimate path cost in the maze
//between two distinct nodes
int heuristic (int r1, int c1, int r2, int c2)
{
}

//send an index and if its not found in the current node list where open is false,
//add this index to openArray and set the open parameter of the this
//nodes as being true (its in the open nodes array)
void addOpens(int i)
{
}

//function to be used in the A* search. it will be used to check the next best
//node to explore based on the lowest F value 
int findLowestF()
{
  //return -1 for the first node (start)

  //loop through the list of open nodes
    //check f value of each index and compare it to the best node starting index at 0
    //set the best var and bestIndex var to j and i respectively if the j node
    //has lower f value then the current best node.

  //loop through all list of open nodes starting at the index of the best node
  //and replace the node at the current index with the one ahead of it,
  //removing it from the list of open nodes

}

//this function is used at the end once the goal cell has been found. the parent
//parameter of each node is used to create the path from the start of the maze
//to the end goal, connecting all the nodes together.
int finalPath(int goal, int r_path[], int c_path[])
{
}

//main section of the A star algorithm
//takes in a start row, start column, a goal row, a goal column
//an array of row positions and and array of column positions
int astarCode (int row_s, int col_s,int row_g,int col_g, int r_path[], int c_path[])
{

  //initialize maze, nodes with their respective locations, default (g,h,f),
  //parent, open, closed values.

  //setup open count and the starting node where the mouse begins in the maze

  //used to check the location of the next node to evaluate in the code below

  //run loop as long as open count is not zero
  
  //find node with lowest f value
  
  //break if no path can be found
    
  //check if the current node is the goal node.
  //if so build the final path

  //take the current node and loop through all neighbors
  //check if robot can move to any of the neighbors

  //move to the next iteration of the loop if the robot can move to the
  //current node being checked and is within the bounds of the maze

  //set up neighbor var of the current node
  //check to see if the neighbor has been set to closed, if not
  //move to the next iteration of the loop

  //set up potential new cost of the neighbor node
  //if the neighbor node is not in the open array, set parent of the 
  //neighbor node as the current node the robot is at, set the cost to go
  //as the potential new cost and set the f value equal to the potential cost
  //plus the heuristic of the neighbor node, add the neighbor node to open array
  //else
  //if the cost to go of the neighbor node is greater than the potential new 
  //cost, this (already seen) neighbor node must be updated similar to the previous
  //if statement before since this node may have a lower cost to go

  //check if the neighbor is not in open array and not a closed node, then the 
  //node is added to opens array as a new node
  //return 0 if no path is found
}

//takes a given node row and column and provides information about the 
//nodes around it depening in which direction the robot is facing.
void sensorMapUpdate(int r, int c)
{  
//can move using the current cell
}

//this function allows the robot to take two arrays that have the row and column
//values needed to check where the robot will go dependent on its heading.
//this also sets updates the heading and the final position that the robot will 
//take once it has made its movements
bool traverse(int r_path[], int c_path[], int length_path, int &r_final, int &c_final)
{
}

void setup() {
  // put your setup code here, to run once:
  //setup digital pins to control sensors and motors

  //create maze with all cells as walls

  // set known starting cell as free
}

void loop() {
  // put your main code here, to run repeatedly:

  //update maze map
  //run the a star algorithm for next best node

  //this section will allow for the robot to move to unknown nodes that have
  //been discovered by the robot if the A* is unable to produce a path

  //move robot approriately based on the path being created


  //if robot is in goal cell, make the robot just idle

  //assign new position to the last movement made by the traverse function

}
