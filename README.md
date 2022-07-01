# Python-Basic-Theta-Star

Python program that finds shortest path from start vertex to goal vertex.

Usage: python basicthetastar.py [input file]

first line of input file is grid size. </br>
second line of input file is start vertex. </br>
thrid line of input file is goal vertex. </br>
fourth line of input file is bottom left vertex of a wall. </br>
any other lines are the bottom left vertices of a wall. </br>

Example input file: </br>
4 9 </br>
0 0 </br>
2 9 </br>
1 6 </br>

Example output: </br>
deque([[0, 0], [2, 6], [2, 9]])
