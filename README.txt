
----------------------------
The University of Manchester
----------------------------

Physics and Astronomy
First Year Lab - Thermal Radiation
Leslie's Cube, Resistance (kOHM) to Temperature ('C) Converter.

(C) Edward Birdsall (Ed Bird) - January 05, 2013.
Report Bugs to edward.birdsall@student.manchester.ac.uk

View readme file for more information. (This is the readme file)

This project is hosted on github:
https://github.com/edbird/LeslieCubeConverter


Operation Instructions.
-----------------------

In your lab, you should have collected data for the resistance of the Leslie Cube, in Kilohms, which corresponds to a temperature.
Rather than interpolate these values manually, use this program.
To run the program, type into a terminal window (for example) './Converter -d data.csv -c conversion-cube4.csv -o output.csv'.
Three options must be specified. These are '-d', a data file, containing your data, '-c', a conversion file, which tells the program how to convert the data, and '-o', an output file which tells the program where to save the output.
Examples of '-d' and '-c' files are given.
data.csv should be a .csv file (create one using a spreadsheet editor like Excel) containing the data collected from your experiment. It should be in Kilohms.
conversion-cube4.csv should be another .csv file containing the conversion data given to you in the lab. You have to create this manually yourself.
output.csv is the output filename. This can be anything you want, but BE AWARE THIS PROGRAM WILL BLINDLY OVERWRITE ANY FILE WHICH ALREADY EXISTS! If you already have a file called output.csv, give the program a different name, such as 'output2.csv' or 'newfileoutput', or 'elephants'.

If you have done everything correctly, then you will get an output file. Open it using Excel, or similar.

To create a .csv file, enter data into Excel, all along one row at the top of the sheet. (It will become quite long if you want the range to be from 20'C to 130'C. It is assumed the data goes from 20'C to 130'C in steps of 1'C. Otherwise it will not work.
Then save this file as a .csv, with the seperator, or delimiter as ',' or "comma".


Important information:
----------------------

Input files must be a list of numbers in the form:

54.3,55.2,43.3

There must be commas between each number, and no comma at either end. There must be no spaces or other characters. Only use commas, numbers 0 to 9 and decimal point. (Fullstop.)


Trouble Shooting:
-----------------

1:) If you do not enter the data in the correct format, the program will probably not work. It might do, but that is by fluke.

2:) If you EXCEED THE CONVERSION RANGE, ie; your input data has numbers bigger than the largest conversion number, or smaller than the smallest, the program will shout at you, and the message will appear:

"Program can interpolate only! (No Extrapolation). Check your conversion file!
y=4.94066e-324 

Conversion Table has been written to file."

Notice the program continued anyway, and blindly gave the output of 4.94066e-324. This is obviously wrong. Sometimes the value of +INF -INF or NAN might come out. It depends on what was in memory before this program loaded.

3:) If you don't specify two existing input files, one for conversion and one for data, this message will show:

"ERROR OPENING FILE
ERROR OPENING FILE
Failed to open file.
-o [OKAY]"

In this case, both input files were not specified correctly and the program stopped. Notice that the output file was specified correctly, and it told us that '-o [OKAY]', ie; the output file opened successfully.

Here is another example:

"Failed to open file.
-d [OKAY]
-c [OKAY]"

In this case the inputs '-d' and '-c' opened successfully, but the output did not.

4:) You fail to specify a '-c' option, a '-d' option or a '-o' option:

"INCORRECT USAGE! Consult README.txt file.
Usage: -d <datafile (csv) inputfile> -c <conversion (csv) inputfile> -o <outputfile>"

In this case, you have ingnored everything in this document, and the program is telling you what to do.

5:) If something else goes bang, email me and I will fix it.