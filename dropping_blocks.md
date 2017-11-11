Reducing [Getting Started with Minecraft Pi](https://projects.raspberrypi.org/en/projects/getting-started-with-minecraft-pi) into
shorter steps to complete in one hour Code Club lesson. 

Aim: To get learners moving with manipulating Minecraft Pi with Python as soon as possible. 

**Steps:**
1. Assemble the Pi.
2. Open Minecraft and create a new world.
3. Open the Python3 IDE
4. Open a new file
5. Cut and paste this code into the new file
```python
from mcpi.minecraft import Minecraft
from time import sleep

mc = Minecraft.create()

flower = 38

while True:
    x, y, z = mc.player.getPos()
    mc.setBlock(x, y, z, flower)
    sleep(0.1)
```
6. Save the file with a meaningful name... `drop_block`.
7. Go to Terminal.
8. Check that you're in the directory where you saved the file.
9. To run the file, type `python drop_block.py` in the Terminal and press return.
10. Go to Minecraft and move about and see if you're dropping flowers..
11. Try flying through the air and see the flowers you leave in the sky.
12. To stop your Python script - either press `Ctrl c` or you need to open another Terminal and type `killall python`.
13. How about you go back to your Python script and change the types of block that you drop.
14. Replace the word `flower` with one of numbers below.
15. Change your script, save it, run again in Terminal and check in Minecraft.
16. Change and repeat. 
17. Have fun. 

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
If finished quickly, check out longer lesson here: [Getting Started with Minecraft Pi](https://projects.raspberrypi.org/en/projects/getting-started-with-minecraft-pi) 
