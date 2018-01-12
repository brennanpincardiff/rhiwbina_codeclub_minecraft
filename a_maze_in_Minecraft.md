Let's try to write a maze lesson for a one hour Code Club lesson. 

Aim: Download file with a CSV maze in it; run the file to make the maze; explore & have fun  

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

Open Python IDE

Open a new file

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
7. Open up Minecraft and create a new world
8. Go to Terminal.
9. Check that you're in the directory where you saved the file.
10. To run the file, type `python maze.py` in the Terminal and press return.
11. Go to Minecraft and see if your maze has been made...
12. Explore.

**Extending the maze:**
1. In Terminal use nano to open and change the csv file... maybe make the maze larger and more interesting...
```
nano maze_rcc.csv
```
2. Add ones and zeros to change the maze - 1 = wall; zeros = air.
3. Control X to save the new maze
4. Save modified buffer by pressing Y
5. Run the script again in Terminal and check in Minecraft.
6. Have fun :smiley:


See documentation for a full list of block types: (http://www.stuffaboutcode.com/p/minecraft-api-reference.html)
If finished quickly, check out longer lesson here: (https://projects.raspberrypi.org/en/projects/getting-started-with-minecraft-pi) 

adapted from "Adventures in Minecraft, 2nd Edition" by Martin O'Hanlon & David Whale
