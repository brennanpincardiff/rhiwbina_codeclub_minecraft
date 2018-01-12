Let's try to write a maze lesson for a one hour Code Club lesson. 

Aim: Download file with a maze in it; run the file  

**Steps:**
1. Assemble the Pi.
2. Connect to the internet
3. Download the file with the maze in it...
Open Terminal
Type this in to download the maze_rcc.csv file
```
wget https://raw.githubusercontent.com/brennanpincardiff/rhiwbina_codeclub_minecraft/master/maze_rcc.csv
```

4. Type this code into the new file
```python
from mcpi.minecraft import Minecraft
mc = Minecraft.create()
import mcpi.block as block

GAP = block.AIR.id
WALL = block.GOLD_BLOCK.id
FLOOR = block.grass.id

FILENAME = "maze_rcc.csv"
f = open(FILENAME, "r")

pos = mc.player.getTilePos()
ORIGIN_X = pos.x+1
ORIGIN_Y = pos.y
ORIGIN_Z = pos.z+1

z = ORIGIN_Z

for line in f.readlines():
    data = line.split(",")
    x = ORIGIN_X
    for cell in data:
        if cell == "0":
            b = GAP
        else:
            b = WALL
        mc.setBlock(x, ORIGIN_Y, z, b)
        mc.setBlock(x, ORIGIN_Y+1, z, b)
        mc.setBlock(x, ORIGIN_Y-1, z, FLOOR)
        x = x + 1
    z = z + 1
```

6. Save the file with a meaningful name... `maze`.
7. Go to Terminal.
8. Check that you're in the directory where you saved the file.
9. To run the file, type `python maze.py` in the Terminal and press return.
10. Go to Minecraft and see if your maze has been made...
11. Can you make your way to the centre.

12. Try opening and changing the csv file... maybe make the maze larger and more interesting...
13. Run the script again in Terminal and check in Minecraft.
13. Have fun :smiley:

**Types of block that you might like to try**

| Number        | Block| 
| :-------------: |:-------------:| 
| 17 | WOOD     | 
| 35 | WOOL     | 
| 79 | ICE      | 

See documentation for a full list of block types: (http://www.stuffaboutcode.com/p/minecraft-api-reference.html)
If finished quickly, check out longer lesson here: (https://projects.raspberrypi.org/en/projects/getting-started-with-minecraft-pi) 

adapted from "Adventures in Minecraft, 2nd Edition" by Martin O'Hanlon & David Whale