Let's try to build a simple building with python for a one hour Code Club lesson. 

Aim: Just a simple building. 

**Steps:**
1. Assemble the Pi.
2. Open Minecraft and create a new world.
3. Open the Python3 (IDLE)
4. Open a new file
5. Type this code into the new file
```python
from mcpi.minecraft import Minecraft
from time import sleep

mc = Minecraft.create()

stone = 1
x, y, z = mc.player.getPos()

# set size of our building
width = 10
length = 10
height = 10


# make our stone block
mc.setBlocks(x+1, y, z, x+width, y+length, z+height, stone)

# hollow it out with air...
mc.setBlocks(x+2, y+1, z+1, x+width-1, y+length-1, z+height-1, 0)

#  hollow out a door
mc.setBlocks(x+(width/2), y+1, z, x+(width/2)+1, y+3, z+1, 0)
```
6. Save the file with a meaningful name... `building`.
7. Go to Terminal.
8. Check that you're in the directory where you saved the file.
9. To run the file, type `building.py` in the Terminal and press return.
10. Go to Minecraft and move about and see if you're dropping flowers..
11. Try flying through the air and see the flowers you leave in the sky.
12. To stop your Python script - either press `Ctrl c` or you need to open another Terminal and type `killall python`.
13. How about you go back to your Python script and change the types of block that you drop.
14. Replace the word `flower` with one of numbers below.
15. Change your script, save it, run again in Terminal and check in Minecraft.
16. Change and repeat - have fun :smiley:

**Types of block that you might like to try**

| Number        | Block| 
| :-------------: |:-------------:| 
| 1     | STONE | 
| 2      | GRASS    | 
| 6 | SAPLING      | 
| 9 | FLOWING WATER      | 
| 10 | LAVA_FLOWING      | 
| 40 | MUSHROOM_RED       | 

See documentation for a full list of block types: (http://www.stuffaboutcode.com/p/minecraft-api-reference.html)
If finished quickly, check out longer lesson here: (https://projects.raspberrypi.org/en/projects/getting-started-with-minecraft-pi) 
