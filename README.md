# Invaders

My version of the Space Invaders arcade game. This game was created as the final project for CS 1110 in Python.

<img src = "Welcome Screen.png" height = "300" width = "300"/>

Credit for pictures of aliens:
Source code provided for the assignment.

Background art credit: 
File: night.jpg
Artist: MarcusGamez
Website: Newgrounds.com, Inc.
Link: https://www.newgrounds.com/art/view/marcusgamez/8-bit-world-at-night
License: Creative Commons: Attribution-NonCommercial 3.0 Unported
The file name was changed from the original.

Credit for picture of the star used as power up:
File: star.png
Artist: artokem 
Website: openclipart.org 
Link: https://openclipart.org/detail/95431/star
License: Creative Commons: Public Domain

Basic Game:

Once the game begins, the aliens march back and forth across the screen. They continue this pattern back and forth, dropping down one step whenever they reach the edge of the screen, until they are all destroyed or make it past the defense line. 

To protect against the invaders, the player can move the ship left (left arrow key) and right (right arrow key) and fire laser bolts (up arrow key). A laser bolt starts from the tip of the ship and moves up in a straight line. If the bolt collides with an alien, that alien is destroyed.

Every time the aliens take step, there is a random chance that one of the aliens will fire a laser bolt back. That laser bolt will always come from the bottom alien in a column chosen at random. If a laser bolt from an alien collides with the ship, the ship is destroyed.

A player has up to three lives, where one life is lost each time a ship is destroyed. If the player has any lives remaining when the ship is destroyed, the game will briefly pause before starting again. The wave continues until one of three things happens:

1. The last alien is destroyed.
2. The ship is destroyed and there are no lives remaining.
3. Any alien touches the defensive line.
In case 1, the player wins the game. In the other two, the player loses.

Extensions:

1. Multiple Waves
If the player completes a wave without losing all the ship lives, a scrolling message will be shown on screen, indicating a new wave. The number of waves in the game is given by NWAVES in consts.py. The box on the screen shows the number of waves left to finish the game and it starts at NWAVES-1. Every time a new wave is started, the aliens need to march faster. The new alien speed is DASPEED*alien speed in the previous wave. DASPEED is a constant in consts.py < 1.

2. Dynamically Speeding up the Aliens
Each time an alien is killed, the speed value of the aliens is multiplied by FACTOR (<1) given in consts.py, thus increasing the speed of aliens marching across the screen. 

3. Keep Track of Scores
The base points for each of the three types of aliens are stored in the list POINTS in consts.py. The points for the aliens near the ship are lesser than the ones far away from it. The base point for the aliens is given as POINTS in consts.py. This value is multiplied into the row number to give the point for a particular alien. The score is carried forward from the previous wave and is displayed on the screen using _scoretext attribute of the Invaders class. 

4. Animate the Aliens
The aliens are animated walking across the screen using filmstrips. 

5. Defense Barriers
The defense barrier has a width 10 and a health meter which shows the health of the defense barrier (value is 100). As long as its health is greater than zero, the barrier can protect the ship against incoming alien bolts. If an alien bolt hits the barrier, its health is reduced by DHEALTH (in consts.py). The barrier changes colors depending on its health. When the health becomes zero, the barrier loses its protective ability and becomes a thin line of width 2. If the health of the barrier is greater than zero, it is carried on to the next wave. If the barrier is destroyed before the next wave starts, the defense barrier begins afresh with a health of 100.

6. Power Ups
There is a class PowerUp that represents power ups. A power up is in the form of a star and can do one of several things: increase the number of lives, add points to the score, and decrease the speed of the aliens moving across the screen. The power ups are launched from the aliens and thus only move in the y direction down towards the bottom of the game screen. If the ship catches the power up, the power up is executed. Else, the power up just continues down and is deleted when it goes out of the game window.  

