# graphxconv
 Graphx Converter v0.5 is a tool for converting BMP images with a size of 256 x 192 pixels to a fixed palette of 16 colors, such as the MSX Screen 2 mode, using the CIEDE2000 conversion algorithm.

The tool converts the source image and saves the new image in MSX format for Mode 2. The conversion may take a few tens of seconds, depending on the power of your computer.

graphxconv: launches on the command line. A graphical interface is then available to view the conversion, and compare this conversion with new conversion parameters or new color palettes.

Several color palettes are available.

2 versions of the basic MSX palette

1 truncated version of the MSX palette for conversion to Black and White.

A palette simulating the display on a C64

A palette simulating the display on a Spectrum

A palette simulating the display on a Game Boy

A two-color palette simulating the black and white display.

Although palettes of microcomputers other than the MSX are proposed, the export of the converted image is currently only in the binary format for MSX (Loading with BLOAD). Other saving templates may be added later.

The command line to start a conversion is: 
graphxconv <Input file> <output file> [-i<n> -p<n> -t<n> -d<n> -c -h]

The first two parameters are mandatory. 
<Input file> : corresponds to the path and name of the BMP file to be converted

<output file>: Corresponds to the path and name of the converted file in MSX format

Other parameters are optional. If they are not specified, the default settings are used. 
-i<n>: if n = 0, this indicates that you do not want to use the GUI. 
	Once the conversion is done and the image saved, the GUI is closed. 
	Any other value, activate the GUI. By default the value is 1 (Ex: -i0)

-p<n>: n, indicates the palette to use for the conversion. 
	By default palette 0 is used. (Ex: -p1) 
	n, can not be greater than the number of palettes included in the program.

-t<n>: n, indicates the color tolerance, during the conversion process. 
	By default the tolerance is set to 100. 
	The tolerance value must be between 0 and 100. (Ex: -t80)

-d<n>: n, indicates the level of detail that will be used during the conversion. 
	By default, the detail level is set to 32. 
	The level of detail must be between 0 and 255. (Ex: d100)

-c: Displays the copyright information. 

-h: displays the help.

The list of palettes included in the software.

0: MSX Palette 0 

1: MSX Palette 1 

2: C64 Palette 

3: SPECTRUM Palette 

4: GAME BOY Palette 

5: B & W Palette 

6: MSX SC2 B & W (Compatible MSX1, Screen 2)

The GUI once 'graphxconv' is launched, is opening a window of 808 x 616 pixels.

The first image displayed at the top left is the original image. Once the conversion is done, on the right of original image converted image will be displayed.

If you are not satisfied with the result, you can try a new conversion by changing parameters, without having to restart the program. Use the following keys:

Key '1': Decrements the color tolerance setting by 20 units 

Key '2': Increases the color tolerance setting by 20 units 

Key '8': Decrements the parameter from the Level of detail by 20 units 

Key '9': Increments the Detail level setting of 20 units

key 'P': Use the following palette (0 -> 6 -> 0 ->) 

key 'S': Insert a new picture slot

key 'ESC' : Exit the program

Each press on a control key, (except ESC and S) restarts a new conversion of the original image, displays the result, and saves the result under the name you specified. 

Each new conversion is displayed over the previous one. If you want to compare multiple versions of the converted image, insert a new image slot by pressing the 'S' key. 

A new portion of the window will emerge, and the next conversion will be displayed in this new Slot. You can open a total of 8 additional slots, and thus compare 8 versions of the converted picture.

