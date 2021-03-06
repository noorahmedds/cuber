## Cuber, a Python implementation of the Rubik's cube

![screenshot](http://i.imgur.com/vvUl1Vz.png)

Cuber is a compact representation of the 3x3x3 Rubik's cube. The primary aim is to be able to
generate scrambles with a certain amount of "bad" edges for practicing the EO-line solving for the
ZZ method. However it is probably possible to use it for other purposes as well. 

Also, I'm a C++ programmer, so the code might not be very pythonic :)

## Usage

Python 2.7, might work with Py3k, I'm not sure (might need to change the print statements here and
there)

You need colorama for the colored output for displaying the cube. 

    pip install colorama

should work.

Development happens on the dev branch, the master branch is (supposedly) stable. 

## Features

  * Generating scrambles
  * Displaying the cube state on the console
  * Executing scrambles
  * Generating scrambles with a known number of bad edges

## Implementation

The stickers are stored in a one-dimensional list. The structure of the cube is represented with
the faces (the face determines the starting index for the stickers) and the faces have "attached
lines" on them which are used to track which stickers have to be moved around when turning a face.
The attached lines are simple 3-tuples of indices. When a face is turned, the stickers associated
with these indices are rotated around in the right direction. The stickers on the face are 
transformed into a 2D matrix, rotated, and then written back to the original array.
