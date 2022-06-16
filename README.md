# Python-Basic-Theta-Star

Python program that finds shortest path from start vertex to goal vertex.

Usage: python basicthetastar.py <input file>

My system will be a robot path planner using the basic theta star algorithm. The user will
be able to send a grid information as input and the system will send back the path found within
the grid. This system will be able to find a short and realistic path in a grid that would be used in
real world applications, such as robot path planning. My evaluation metric for success will be
how efficiently the theta star algorithm finds the path.
The input needs to be an input file. In this file, the first three rows each contain two
integers where 0 <= m, n <= 1,000,000. The first row ‘m n’ will represent the grid size where m
is for the number of row vertices plus one row in the grid and n is for the number of column
vertices plus one column in the grid. The second row ‘m n’ will represent the start vertex on the
grid where m is the row vertex index and n is the column vertex index. The third row ‘m n’ will
represent the goal vertex where m is the row vertex index and n is the column vertex index. All
of the rows ‘x y’ after the third row where 0 <= x < number of rows, 0 <= y < number of
columns, will represent the bottom left corner of walls in the grid where x is the row vertex index
and y is the column vertex index. Walls will be initialized in the program to have a bottom left
corner, top left corner, top right corner, and bottom right corner according to the bottom left
corner that was given in the input file. All of the rows after the third row are optional. If a path
can be found from the input, a deque list of vertices [[c, d], …, [a, b]] will be displayed as output
where [c, d] is the start vertex and [a, b] is the goal vertex. The first vertex in the output list will
be the start vertex and the last vertex will be the goal vertex. There may be an arbitrary amount
of vertices in between the start vertex and the goal vertex which will depend upon how many
times the parent vertex changed along the found path. If a path cannot be found, then the output
will be FAILURE.
Example text in input file:
4 9
0 0
2 9
1 6
Example output:
deque([[0, 0], [2, 6], [2, 9]])
Example text in input file:
4 9
1 4
2 9
0 3
1 3
0 4
1 4
Example output:
FAILURE
My model will be a 2-dimensional grid. This grid will contain a start vertex labeled
START and a goal vertex labeled GOAL. This grid may also optionally contain walls that are
black squares. The path must start from the start vertex and end at the goal vertex. The path may
not go through walls.
My algorithm for finding the path in the grid will be the basic theta star algorithm. This
algorithm propagates information along grid edges without constraining the path to grid edges.
This allows the algorithm to have a short runtime and find any-angle paths(Likhachev 1). This
means that if a parent vertex has line of sight to its successor vertex in the grid, the path will go
directly from the parent vertex to its successor vertex. A successor vertex is not in line of sight
from its parent vertex if the line segment between these two vertices traverses cells that contain
walls, passes between cells that contain walls that lie on the same grid edge, or passes between
walls that share a corner on the grid.
Example model:
Path found in model by using basic theta star algorithm:
The algorithm will first start at the start vertex (0, 0). The neighbor vertices will keep
expanding from the start vertex until all vertices have been searched or the goal vertex has been
found. The start vertex will be the parent vertex of every expanded vertex if the vertex is in line
of sight to the start vertex. The line of sight from the start vertex (0, 0) to vertex (2, 7) where the
line traverses the wall is the shortest path found so far when vertex (2, 7) was expanded and that
is where the line of sight ends from the start vertex to vertex (2, 6). The parent vertex for vertex
(2, 7) will be set to (2, 6) because vertex (2, 7) was the successor of vertex (2, 6). The vertices
will keep expanding until the goal vertex (2, 9) has been reached. The path has been found by
using the basic theta star algorithm.
The challenges will include how the graph will be traversed. A topic to address this
challenge will be the basic theta star algorithm that will traverse the graph. This algorithm will
contain a euclidean distance function to calculate the distance between vertices. This algorithm
will also contain a line of sight function to determine if a vertex is visible or not from another
vertex. A pro for this algorithm is that it is efficient and finds short and realistic paths. A con for
this algorithm is that it does not guarantee to find the shortest path.
There are systems that already exist that are very similar to my system. One system uses
the basic theta star algorithm for path planning of a mobile robot on a grid map(Duchon 61). Path
planning of a robot concerns moving a robot from one point to another point(Duchon 60). Robot
path planning requires a grid as input that may contain obstacles for the robot to avoid and the
output would be the optimal path found in the grid(Duchon 63). This system in the paper that I
found and my system are complementary because it uses the same algorithm. Another system
that I found also uses the basic theta star algorithm for path planning in computer games(Nash
1). This algorithm is much better than the astar algorithm for path planning because basic theta
star algorithm considers paths that are not constrained to grid edges during the search and is able
to make more informed decisions(Nash 7). Although the algorithm does not guarantee to find the
shortest path, it is simple, fast and finds shorter and realistic paths compared to the astar
algorithm(Nash 1). This system is complementary to my system because it uses the same
algorithm.
Citations
Duchon, Frantisek. Babinec, Andrej. Kajan, Martin. Beno, Peter. Florek, Martin. Fico, Tomas.
Jurisica, Ladislav. “Path planning with modified A star algorithm for a mobile robot”, Modelling
of Mechanical and Mechatronic Systems MMaMS 2014, 2014,
https://reader.elsevier.com/reader/sd/pii/S187770581403149X?token=231BA8C9980B106ECBB
94FFB06313F2AAF8E8D6D3C5FDADFD6B9F3AE920E73743E4560D17EB4D4A189E2133
A02E6D18C&originRegion=us-east-1&originCreation=20211029015047. Accessed 28 October
2021.
Nash, Alex. Daniel, Kenny. Koenig, Sven. Felner, Ariel. “Theta*: Any-Angle Path Planning on
Grids”, https://www.aaai.org/Papers/AAAI/2007/AAAI07-187.pdf. Accessed 04 December 2021.
Nash, Alex. Koenig, Sven. Likhachev, Maxim. “Incremental Phi*: Incremental Any-Angle Path
Planning on Grids∗”, http://www.cs.cmu.edu/~./maxim/files/inctheta_ijcai09.pdf. Accessed 04
December 2021.
