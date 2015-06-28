# tshape_analysis

This script contains code for several shape analysis metrics designed to be used on contours taken from ultrasound images of the tongue.

The analysis metrics are:

* Procrustes analysis
* Modified Curvature Index
* Fourier analysis of the tongue profile

The code is written in Python. 

## Data type and output file

* The data this script is designed to run on consists of .csv files containing x and y coordinate points for a series of tongue shape contours. The filename/s of the .csv files should be structured as: identifier_symbolforsegmenttype.csv (e.g. ‘01FC_ara’ where 01FC is the participant, and ‘ara’ is the stimulus item or segment type).

* The script assumes the first column of data in the .csv is the x coordinates for the first shape, and the second column is the y coordinates for the first shape. Subsequent columns in the same .csv file are for additional shapes.

* If your .csv files have header lines, the n_header_lines parameter (by default set to 0) can be used to ignore the header data in your files.

* To run the Procrustes analysis, there must be a file in the directory containing the resting, or baseline comparison shape. The name of this file must be structured as: identifier_rest.csv. If this file is not available, no Procrustes analysis will be performed.

* The default output filename is: shape_analysis_data_out.csv. The output file contains a row for every contour, and includes the following data: 
  * ID (taken from filename) 
  * symbol (taken from filename)
  * repetition (based on location in .csv file)
  * MCI - Modified Curvature Index value
  * procrustes - Procrustes Analysis value
  * real_1 - real part of 1st Fourier coefficient
  * imag_1 - imaginary part of 1st Fourier coefficient 
  * mod_1 - modulus (magnitude) of 1st Fourier coefficient 
  * real_2 - real part of 2nd Fourier coefficient
  * imag_2 - imaginary part of 2nd Fourier coefficient 
  * mod_2 - modulus (magnitude) of 2nd Fourier coefficient 
  * real_3 - real part of 3rd Fourier coefficient
  * imag_3 - imaginary part of 3rd Fourier coefficient 
  * mod_3 - modulus (magnitude) of 3rd Fourier coefficient

## Instructions for use

* The script expects the .csv files containing the data to be in the current working directory.
* The script can be run in Python or in a terminal window 
* If you use the terminal window, type in the file path (including the filename) for ‘shape_analysis.py’. Press Enter to execute the script.
* If you are in Python, type: `import shape_analysis` then `shape_analysis.doIt()`




**The authors make no promise of continued support or development of the code contained in this repository.**
