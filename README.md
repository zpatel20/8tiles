# 8tiles
Board
Used to store the board pieces, initialize a board, compute the board heuristic value, find possible next moves from any board position.  If you do use a data structure that needs a hash value, you should define that as well.  Unless the board is initialized by the user, the Board class should create a board where the destination pieces are chosen at random.  Seed your random number generator using:    
        randomGenerator.setSeed( System.currentTimeMillis());
so that you get different boards each time you run the program.
TilesDriver
This is the driver for the rest of the program and contains main().  Use this to test the other classes as they are created.  The loop to play the game interactively (or automatically solve the puzzle) is inside this class.  Move validation is controlled from here.
Node
Nodes are what are stored in the SearchTree.  Each node should have a Board as well as elements needed to connect Nodes to each other, as needed.
SearchTree
This implements the A* state-space search algorithm which uses a heuristic as an approximation of the goodness of each board configuration.  If the chosen heuristic is overly optimistic, then that implies less search, but at the possible extent of an optimal solution.  A heuristic is admissible if it underestimates the goodness of a position.  This implies extra search, but that search then encompasses an optimal solution.
The search tree should include some sort of storage for: 
The list of all unique Nodes
This can be any sort of data structure, but efficient Node lookup is important, since this is the data structure you will use to process and store only new unique Nodes that are not already on this list, out of the total possible ~181,442 moves.  You could maintain this as an ordered list by hash number and use binary search, or you could use a HashMap.
The ordered list of leaf Nodes
This could be stored as an ordered linked list or as a Priority Queue.  Here the ordering is done by heuristic value, with a lower heuristic value being preferable.  The heuristic is the sum of the city-blocks distances of each piece from its desired destination.
Constants
If you have constants shared with multiple classes they should be declared in the Constants class.
