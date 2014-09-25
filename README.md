					jSON_Walk.py
============
Why?

gdal2tiles.py creates an enormous folder structure of .png files meant to represent a Tile Map.  The file and directory names are generated dynamically and represent the geographic location of each small tile.  Therefore, if you want to download a folder of tiles, you need to know the name and location of each file.

============
How?

jSON_Walk.py is to be run in directory containing the gdal2tiles.py-created folders.  It will output a file called 'plateContents.json' which is a jSON Object whose structure is as follows

{key:value, key:value, ...}
The key represents the name of each folder of Tiles within the directory jSON_Walk was run.
The value is an array of each file and its path within the key-folder.

===========
Example

In a folder containing:
jSON_Walk.py
Plate22.01/8/63/156.png
Plate22.01/8/64/156.png
Plate22.01/10/256/620.png
Plate22.01/10/256/621.png
Plate23.02/10/8/63/156.png
Plate23.02/10/8/63/157.png

>python jSON_Walk.py
creates a file called 'plateContents.json' that should contain the following:

{"Plate22.01":["/8/63/156.png","/8/64/156.png","/10/256/620.png","/10/256/621.png],"Plate22.02":["/10/8/63/156.png","/10/8/63/157.png"]}

============
About:

Written using Python 2.7
Jason Aylward
25 Sept 2014
jason.aylward@gmail.com




	  	

 
