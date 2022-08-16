roguelike-dungeon-generator
===========================

An algorithm that generates a level for roguelike games.

There's also a [C# port](https://github.com/mizipzor/DungeonSharp).


Outline
=======

1. Divide the map into a grid of evenly sized cells.
2. Pick a random cell as the current cell and mark it as connected.
3. While the current cell has unconnected neighbor cells:
    1. Connect to one of them.
    2. Make that cell the current cell.
4. While there are unconnected cells:
    1. Pick a random connected cell with unconnected neighbors and connect to one of them.
5. Pick zero or more pairs of adjacent cells that are not connected and connect them.
6. Within each cell, create a room of random shape.
7. For each connection between two cells:
    1. Create a random corridor between the rooms in each cell.
8. Place staircases in the cell picked in step 2 and the lest cell visited in step 3ii.


Example output
======
```
             ######                    ############# ######
    ######## #....#         ########   #...........###....#########
    #......###....###########......#   #...##.......##............#
    #..............##......##......#####...##.............###.....#
    #......##......##......................##......###....# #.....#
    #......###.....##......##......##########......# #....# ####.##
    #......# #.....##......#########        #......# #....#   #..#
    ####.### #####.#####.###                ######## ###### ###.##
      #..#       #.#####.## ######          #####           #...##
     ##.####   ###.##.....# #....#          #...#         ###....#
     #.....#   #..........# #....############...#      ####......#
     #.....#   #...##.....# #..............#....#      #....#....#
     #.....#   #...##.....# ###.######..........#      #...##....#
     #.....#   #...##.....#   #.#    #.....####.#      #...##....#
     #.....#   ############   #.#    #.....#  #.#    ###...##....#
     #####.#                  #.###  #######  #.#    #...######.##
       ###.# ######         ###...##        ###.##   #.###   ##.###
       #...# #....#  ########......#        #....#  ##.##### #....#
       #...###....#  #.....##......##########....#  #......# #....#
      ##...##.....#  #.....##......##......##....#  #......# #....#
      #...........####.............##......##....#  #......###....#
      #....###.............##......##......##....#  #.............#
      #.#### #....####.....##......##............#  ##########....#
      #.#    ####.#  ##################.##########           ##.###
      #.#    ####.## ######           #.####                  #.#
      #.#    #.<...# #....##########  #....#                  #.####
    ###.##   #.....###.............#  #....######### ######   #....#
    #....#   #.....##.....##.......#  #............# #....#   ##...#
    #....#####.....##.....##.......#  #....###.....# #....######...#
    #..............##.######.......#  #....# #.>...# #.............#
    ##.#######.....##.#    #.......#  ###### ####### #....######...#
     #..#    ########.#    #####.###                 ##.###    ##.##
     ##.####        #.######   #.#   #######         ##.##     ##..#
     #.....# ########......#####.#   #.....#         #...#     #...#
     #.....###.............##....#   #.....#         #...#     #...#
     #..............#......##....#####.....######### #...#     #...#
     #########.....##......##......................###...#     #####
             #.....##......##...#############............#
             ########......######           #......###...#
                    ########                ######## #####
```


Credits
=======

Created as I reworded [this algorithm](http://kuoi.org/~kamikaze/GameDesign/art07_rogue_dungeon.php) (link is now broken, can't find a mirror) to make it easier to follow.
