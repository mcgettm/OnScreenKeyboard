On Screen Keyboard
==================

How to Use
----------
This console application accepts two parameters. The first parameter is the input file. The second parameter is an output file and it is optional. The output will also be displayed in the console.

Solution Overview
-----------------
I structured the solution into two pieces. The OnScreenKeyboard project has an InputProcessor class that can take the input string and convert it into the output string. The InputProcessor accepts a Keyboard object that implements the IKeyboard interface in its constructor. The Keyboard object has a method that scripts the path between two characters. 
By structuring it this way, we can easily re-use the InputProcessor with different keyboard layouts. The InputReader project contains the DVRKeyboard class being used for this exercise. It consists of a dictionary of KeyboardButton objects that are indexed by the character the button represents. Each KeyboardButton has an x and y coordinate value.
The GetPath method takes the two characters we need to get the path between and identifies the corresponding buttons in the dictionary. Then, using the x and y coordianates, we can build the path needed.

The Problem
-----------
On screen keyboards are the bane of DVR users. To help alleviate the pain, one local company is asking you to implement part of a voice to text search for their DVR by developing an algorithm to script the on screen keyboard.
The keyboard is laid out as follows:

```
ABCDEF
GHIJKL
MNOPQR
STUVWX
YZ1234
567890
```

Please write a program which scripts the path of the cursor on the keyboard. The program should: 

1. Accept a flat file as input.
	1. Each new line will contain a search term
2. Output the path for the DVR to execute for each line
	1. Assume the cursor will always start on the A
	2. Use the following characters to make up the path
		1. U = up
		2. D = down
		3. L = left
		4. R = right
		5. S = space
		6. \# = select
3.	Comma delimit the result

Sample Input
------------
IT Crowd

Sample Output
-------------
D,R,R,#,D,D,L,#,S,U,U,U,R,#,D,D,R,R,R,#,L,L,L,#,D,R,R,#,U,U,U,L,#

The Fine Print
--------------
Please use whatever technology and techniques you feel are applicable to solve the problem. We suggest that you approach this exercise as if this code was part of a larger system. The end result should be representative of your abilities and style.

Please fork this repository. When you have completed your solution, please issue a pull request to notify us that you are ready.

Have fun.