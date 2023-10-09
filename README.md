# STC
***Python Data Pipeline for “XXXX” Paper Data Analysis***
***Written for Python in Jupyter*** 
*** Licence information here***

This set of programs processes raw Ca2+ imaging data and raw mouse behavioural data to: (i) identify place cells in the raw Ca2+ imaging data; (iii) determine rate maps for the activities of each cell in each session; and (iv) determine the correlations between rate maps across sessions. 

Program 1 takes as input the raw Ca2+ imaging data (output by XXXX in .csv form) and the raw behavioral data (output by XXX in .xslx form), and cleans the data, including interpolating values of the behavioural data at the Ca2+ imaging times (as the Ca2+ data and behavioural data are sampled at different rates).

Program 2 takes as input the cleaned data from program 1, and labels the cells in the Ca2+ data as either place cells or not place cells based on a comparison of their spatial information to the spatial information of shuffled data. 

Program 3 (there are two versions, depending on whether 4 or 6 behavioural sessions are used) takes as input the cleaned data from program 1 and the place cell identification from program 2, determines the total per-session activity for each cell, and creates a combined table of the total activity and the place cell identification. 

Program 4 (there are two versions, depending on whether 4 or 6 behavioural sessions are used) takes as input the cleaned data from program 1 for all the sessions for a mouse, determines the rate maps for each cell, and performs Gaussian smoothing on the rate maps.  

Program 5 (there are two versions, depending on whether 4 or 6 behavioural sessions are used) takes as input the Gaussian smoothed rate maps for all the sessions for a mouse, and determines the session 1-3 correlation and session 2-4 correlation. It also plots the smoothed rate maps for a given cell.

Program 6 takes the output of program 3 and combines it with the output of program 5 to produce a table that includes, for each cell of a mouse: cell identity; place cell identification; session correlations; and total activity per session.   

  Copyright (c) 2023 Yuki Sakai

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
