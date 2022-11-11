# VG101_2020SU_term project Brief Report
# Commandline Bomber Man Game 
## Group Introduction
Xiaoyang Sheng  
Email: sheng6188@sjtu.edu.cn  
Zeyu Yang  
Email: yangzeyu1026@sjtu.edu.cn  
Yibo Wu  
Email: jacky1319@sjtu.edu.cn  
## Project Introduction
### Name: Simplified Bomberman  
#### Intended language: C/C++  
#### Summary: 
After learning the basic knowledge of C language, we are going to implement the simplified version of a classic game called bomberman by achieving the basic function of the game.  
#### Motivation: 
The Bomberman is a very classic game which was first published in 1983 and popular worldwide. After that, many other games with the similar mechanics are published and got popular in the early age of the web game. After learning some basic knowledge of Clanguage in this course, our group decided to implement a simplified version on our own so that we can both get trained and enjoy this classic game.

## Design
### File I/O and Map Designing:
We choose to use file I/O to fulfill our map loading. For one thing, it can effectively reduce our code in the main function. For another thing, we design several kinds of maps with different difficulty levels conveniently. Player can even design their own maps when necessary. (Please refer to README.md for further instructions.)  
We use standard file input and output to accompolish our map load. To simplify our text file, which is the map file. We build a one to one mapping from the signs on the map to a range of numbers. We design three maps based on the numbers of walls and on how strong the wall is.  
In the program, we use the variable FILE to read in the text file we have designed. FILE is a pointer variable, which can make input act similar to standard input on screen. We wrap all these steps in functions called readinmap and makes the code more well-structured.
### Keyboard Manipulation: 
In our game, users can control the player roles by directly interacting with keyboard, for keyboard is diverse and fit for two players to play together. This also corresponds to the most popular games recently.  
We use kbhit function to get instant input from the keyboard. This ensures players’ instant command. We use if-else statement to determine which character does the player type in. Nowadays, most games employ manipulation just as the table 1 shows, we did the same thing in our game. All these steps are in the main function since these are prelude to the main game codes.  
### Two-player Mode:
We design two-player mode to make our game more competitive. Players can compare their manipulation as well as luck during the game.  
We construct a structure array containing two elements standing for two players. In the struncture, there are elements such as healt and power. As a result, all the elements in the structure array acts similarly. We also design functions to enable our players to choose various initialization, for some players may want more health level, some may want more power.  
### props: 
Props are important because they add to the diverse game. In this game code, we employ several two-dimensinal arrays, integer type or character type, to represent different layers of the map. We choose to display the layer we need to the screen. If we set bomb to make some walls break, we display the prop after the breakable wall is broken down. If there happen to be no prop, we display nothing.  
As to the randomness of the prop, we use classical random number generator where we set time as our random number seed. When it comes to use the random numbers, we use the random number to mod 5 to get a random integer in the range from 0 to 4, each number maps to a certain prop. If the player array happens to go through the prop array, which means their coordinates are identical, the player array will receive the command form the prop array. As a result, the feature of player arrays are changed.  
### Information Bar:
To get instant situation of each player, we must have something always reminding the players how is their health level, how is the power of their bomb, etc.  
We display the information bar in the string. Since we apply the double buff screen, we have to set all our information in a string, which means we have to convert some integers into characters. We use the itoa function and we write our own string merge function to fit our use.
### Timer:
Since our games is about explosion and the explosion time can be changed by getting some props, it is necessary to design a timer throughout the entire game. After a player has settled the bomb, we therefore has a specific struct to recording explosion. We use clock function to record time, then modify what is being shown on the map.
### Double Buff Screen:
Cmd in windows is famous for its shimmering, which is bad for players’ eyes as well as their game experience. We therefore have to find ways
to solve such proplems.   
We create another screen in the buff region. One screen reveals what needed to be shown, in the meantime, the other has already loaded what is going to be shown in a very short time. But it is this short time matters. By changing the two screens, we manage to make the screen not shimmer.
