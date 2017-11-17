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

x, y, z = mc.player.getPos()

# set size of our building
width = 10
length = 10
height = 5


# make our stone block number = 1
mc.setBlocks(x+1, y, z, x+width, y+length, z+height, 1)

# hollow it out with air...
mc.setBlocks(x+2, y+1, z+1, x+width-1, y+height-1, z+length-1, 0)

#  hollow out a door
mc.setBlocks(x+(width/2), y+1, z, x+(width/2)+1, y+3, z+1, 0)
```
6. Save the file with a meaningful name... `building`.
7. Go to Terminal.
8. Check that you're in the directory where you saved the file.
9. To run the file, type `python building.py` in the Terminal and press return.
10. Go to Minecraft and see if your building has been made...
11. Try changing the size or what the building is made of...
12. Change your script, save it, run again in Terminal and check in Minecraft.
13. Change and repeat - have fun :smiley:

**Types of block that you might like to try**

| Number        | Block| 
| :-------------: |:-------------:| 
| 17 | WOOD     | 
| 35 | WOOL     | 
| 79 | ICE      | 

See documentation for a full list of block types: (http://www.stuffaboutcode.com/p/minecraft-api-reference.html)
If finished quickly, check out longer lesson here: (https://projects.raspberrypi.org/en/projects/getting-started-with-minecraft-pi) 
