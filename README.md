This project generates mazes. It serves as the final project for CMPS-2200.

The program uses a collection of random graphs, drawn via Pigale.
We parse the parse the graphs as Networkx graphs.
Then, we calculate a spanning tree of "open" edges that form a maze. We can throw in some extra open edges too.
The maze object contains this physical maze along with the locations of the nodes.
We also keep track of a "known maze" that encodes the part of the maze that has been explored.
Finally, we have a "hero" class that keeps track of distance traveled and deadends hit.

The algorithms to implement for the project belong in maze_solve_algorithms and maze.

Here, we give an overview of the files and the notable classes and functions in each file. The files are listed in order, so that each file imports all of the previous files. The students must write the functions labeled with *.

File . . . . . . . . . .Important classes/functions. . What they do
--------------
draw_and_parse_graph . .parse_graph. . . . . . . . . . Creates a Networkx graph from graphml file.
. . . . . . . . . . . . graph_drawer(class). . . . . . Draws graphs with matplotlib. Handles updating the drawing.
maze_design algorithms. fisher_shuffle*. . . . . . . . Creates a uniformly random permutation.
. . . . . . . . . . . . kruskals* . . . . . . . . . . .Finds a minimal spanning tree.
. . . . . . . . . . . . update_shortest_distances . . .Maintains a dictionary of all-pairs shortest paths.
. . . . . . . . . recover_path_from_shortest_distances gives the shortest path between known nodes.
maze . . . . . . . . . .maze(class). . . . . . . . . . Represents the physical maze with some closed edges.
. . . . . . . . . . . . known_maze(class) . . . . . . .Represents our knowledge of the maze.
. . . . . . . . . . . . hero(class) . . . . . . . . . .Represents a person in the maze. Tracks statistics.
maze_solve_algorithms. .depth_first_search* . . . . . .Causes hero to search graph, depth-first.
. . . . . . . . . . . . a_star_search* . . . . . . . . Causes hero to search the graph using a_star_algorithm.
. . . . . . . . . . .linear_programming_shortest_path* Finds the shortest path through a known maze with LP.
examples . . . . . . . .text_explore . . . . . . . . . draws the graph as you move through it by text.
tests . . . . . . . . . Tests(class) . . . . . . . . . Tests the code.