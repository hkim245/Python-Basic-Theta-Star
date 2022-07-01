# Python-Basic-Theta-Star

Python program that finds shortest path from start vertex to goal vertex in a grid.

Usage: python basicthetastar.py [input file]

first line of input file is grid size. </br>
second line of input file is start vertex. </br>
thrid line of input file is goal vertex. </br>
fourth line of input file is bottom left vertex of a wall that will create a wall. </br>
any subsequent lines are the bottom left vertices of a wall that will create a wall. </br>

A wall consists of a bottom left vertex, top left vertex, top right vertex, and a bottom right vertex that fills a cell in the grid.

Example input file: </br>
4 9 </br>
0 0 </br>
2 9 </br>
1 6 </br>

Example output: </br>
deque([[0, 0], [2, 6], [2, 9]])

Output shows the vertices used in the path from start vertex to goal vertex. The vertices can be connected with straight lines to show the shortest path found.

Citations: </br>
https://reader.elsevier.com/reader/sd/pii/S187770581403149X?token=231BA8C9980B106ECBB </br>
https://www.aaai.org/Papers/AAAI/2007/AAAI07-187.pdf </br>
http://www.cs.cmu.edu/~./maxim/files/inctheta_ijcai09.pdf </br>
