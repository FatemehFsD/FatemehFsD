# What is the project?

## This algorithm is for alignment of biological networks and it aligns nodes based on their similarities to their neighbours. It receives two networks and the similarity file of them as input and then computes the aligned nodes based on the similar neighbours. However, to make it more understandable there are two simple networks with reduced nodes and edges to demonstrate more clearly. 
The name of the algorithm is Wave that is for alignment in biological networks.

# How does the algorithm work?

## The algorithm gives priority to the nodes with simillar neighbours for the alignment. It first finds the similar nodes and then put priority to the nodes with similar neighbours. In the begining, all the nodes are signed as unvisited, then similar nodes based on the value are being considered to expand their neighbours. Then, neighbours are counted to align similar nodes.  

the  argmax function recieves the vote matrix as the input and calculates the maximum value of the vote( those nodes that are unaligned and have the maximum similarity):
double argmax(double vote[NumOfNodOfFirstNet][NumOfNodOfSecondNet])

the saveNetSecond function reads the second network from the file and save it as a matrix named myNode2
void saveNetSecond()

The saveNetFirst function saves the first network in the matrix (the two dimention array) myNod:
void saveNetFirst() 

in the below function the right neighbours of the file are the result; it means that when the left nodes of file are the input, the right nighbours are the output of this function:
void findingNeighbours2(int ii2)

the below function is being used for displaying the adjacency list of the networks
void displayAdjList(list<int> adj_list[], int v)
  
this function adds edges of the networks into the list named adj_list
void add_edge(list<int> adj_list[], int u, int v)  (it adds v into the list u, and u into list v)
  
this function reads the similarity file and saves the values into a matrix or 2 dimentional array named simi[][]
void readsimi()

In the main:
  the first main part creates the edges from the nodes that they are neighbours
  then the other next part saves the similarity matrix into the vote matrix with mulltiply the similarities in a parameter
  afterward, it calculates the maximum value of the vote matrix that are unvisited for each iteration
  In the next step, it makes the vote matrix updated based on new similarities
  then, it shows the output which is an array of alignments, indexes are nodes of the first networks and the values of the array are the aligned nodes of the other network


# How to run?

## First, there are 4 files named: simi, test.net.bigger, test-network and wTask2 that should be dowloaded. Then visual studio version 2017 and later years are suitable to open a new console c++ project, and copy the codes in wTask2 inside it and run. 

## Inputs are simi, test.net.bigger and test-network files. The input format are .txt files that contains 2 input networks and one similarity file of those networks. Each input network contains the edges of that network, each edge is named by two nodes, and nodes are named by integers. Therefore, each input file in the first line indicates the number of nodes and then edges, and in the rest lines each edge is written by the nodes as a pair integers. In the similarity file in each line is indicated the node of one network and the node of another network as integers with the similarity value. Output is on the debug window.

# Attention

## This code is a part of a bigger project, so the preprocess part to create the similarity file is separated. Also, the output of this part is processed for evaluation in a different process. 
