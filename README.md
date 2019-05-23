# 1410-Assignment-10
Lights Out
Visit this link (Links to an external site.)Links to an external site. to familiarize yourself with Lights Out.  The playing board is a 5x5 grid of lights.  A light is either on or off.  When you click on a light, the on/off state of that light---as well as the lights above, below, to the left, and to the right of it---toggle.  The goal of the puzzle is to turn all of the lights off.

Lights Out GUI

Your GUI must:

Be reasonably attractive.

Have a 5x5 grid of controls to serve as the playing board.  You can use different colors or images or some other mechanism to distinguish lights on/lights off.  However, it should be obvious whether a square is "on" of "off".  If you are using colors, use a light color for "on" and a dark one for "off".

Have a "New Game" button that randomly creates an initial game position.  It must be possible to win the game from this position.  To ensure that it is possible to win, start with a board in which all of the lights are off and then simulate a sequence of random moves.  You can call the nextInt method on a java.util.Random object to generate random integers.  If instead you randomly set the initial state of each control, you will probably produce a position that can't be solved.

Have an "Enter Manual Setup" button.  When clicked, the text of the button should change to "Exit Manual Setup" and the game should enter manual setup mode.  In this mode, clicking on a grid control should toggle only the grid control being clicked, not any of its neighbors. When the "Exit Manual Set" button is clicked, the button text should change back and normal game play should resume.  The purpose of manual setup mode is to allow a player to configure a game any way he or she pleases.

Report when the player has won the game (turned all the lights off) by displaying a dialog box.  Wins should not be reported during manual setup mode,  nor should they be reported when that mode is exited with all lights turned off.  (Here (Links to an external site.)Links to an external site. is an algorithm for solving any solvable position.  It will come in handy when you test your game by playing it.)

Close the window and shut down the program when the window's X icon is clicked.
 

Program Structure

Use the ConnectFour game from PS8 as your inspiration for your Lights Out game.  Your program is to be divided into four files, for ease of grading.  Put your source files into package lightsout.

LightsOutView.java should contain the components of the program that create and display the GUI interface and react to mouse clicks by calling methods on a LightsOutModel object and updating the display.  No knowledge about the rules of Lights Out should be incorporated into LightsOutView.java.  Do not use JButtons in the main 5x5 grid.  I'll explain why below.

LightsOutModel.java should provide an object that can be used to keep track of the state of a Lights Out game.  It should know nothing about, nor make any use of, the GUI elements.  The idea is that LightsOutView and LightsOutModel have completely different responsibilities, but they coordinate with each other (via method calls from LightsOutView to LightsOutModel) to provide the game implementation.  (In the ConnectFour game, C4Display is analogous to LightsOutView, and C4Board is analogous to LightsOutModel.)

LightsOut.java should contain the main method that launches the game and nothing else.

LightsOutModelTests.java should contain JUnit tests for the class(es) in LightsOutModel.java.  (You are not required to write unit tests for the GUI-oriented classes in LightsOutView.java.)
Implementation Hints

Use a GridLayout to create a JPanel containing the 5x5 grid of lights.

Do not fill the 5x5 grid with JButtons.  (The problem is that button coloring doesn't work very well on Macs.  Even if you are not using a Mac, your grader may be.)  Instead, use JPanels and their addMouseListener method.  See C4Board.java from PS8 for an example of how to do this.

Use a BorderLayout to format the entire application.  Put the panel with the 25 squares into the center of the BorderLayout, and put the other buttons along the bottom or top edge.
Be sure to follow all of our usual commenting and code formatting standards.

 

Minesweeper
In this part of the assignment you will be repairing a bug in our version of Minesweeper, a classic game that most people have played.

Double click on Minesweeper.jar in the project folder to run Minesweeper.  The File menu (mostly) works; the other menus are just for show and don't do anything.  To start a new game or to reveal everything about the current game, use the buttons at the bottom.

How to play the game.  The goal of Minesweeper is to uncover all the squares on the board that do not have a mine. If you do, you win. If you hit a mine, you lose. To play the game, you click one square at a time and continue clicking until you win or lose. When you click, sometimes one square will be uncovered, other times, many squares will be uncovered. To help you complete this task, the game gives you hints by telling you how many mines surround each square. You will only see these numbers when the square is uncovered. When you start the game, your first click, and possibly a few more, will be completely random. After many squares are uncovered, you can use the numbers and mathematical logic to determine which square to choose next.

Rules of the game.

If you left-click and uncover a square with a mine, you lose the game. To continue playing, you must click New Game and start over.

If you left-click and uncover a square without a mine, and the square has at least one adjacent mine, then the number of adjacent squares that haves mines will be displayed in the square.

If you left-click and uncover a square with no mine and no adjacent mines, then that square will be blank (have no number).  The contiguous region of blank squares to which it belongs, including its non-blank boundary, is revealed.

If you right-click on a square, then it will be marked with a flag that signified that you think a mine is located there.

If you right-click on a square that has been marked with a flag, it will changed to a question mark, denoting that you are unsure if a mine is located there. It will stay covered.

If you right-click on a square with a question mark, the question mark will be removed.
 

Your task.  The randomly generated playing field contains very few mines, which means that it contains large blank regions.  Play the game a few times to see what I mean.

Now turn your attention to the minesweeper package and run the MinesweeperRUN class.  This version works just like Minesweeper.jar except that when you click on a square that does not contain a mine, nothing is revealed.  Which is kind of annoying.

Your job is to modify the program so that it works properly.  All you will need to do is complete the MinesweeperModel.uncoverEmptyRegionAndBoundary() method. 

Recursion is your friend.  Have fun!
