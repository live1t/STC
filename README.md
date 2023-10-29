# STC
**Python Data Pipeline for “Synaptic tagging and capture underlie neuronal co-allocation and temporal association memory in behaving mice” Paper Data Analysis**
**Written for Python in Jupyter (v7.0.6)**
**Tested on MacBook Pro running MacOS Big Sur v.11.6.1, M1 chip, 16GB RAM**
**No non-standard hardware required**

This set of programs processes raw Ca2+ imaging data and raw mouse behavioural data to: (i) identify place cells in the raw Ca2+ imaging data; (iii) determine rate maps for the activities of each cell in each session; and (iv) determine the correlations between rate maps across sessions. 

Program 1 (Interpolation) takes as input the raw Ca2+ imaging data (output by IDPS from Inscopix in .csv form) and the raw behavioral data (output by Ethovision in .xslx form) as defined b yth einput pathways, and cleans the data, including interpolating values of the behavioural data at the Ca2+ imaging times (as the Ca2+ data and behavioural data are sampled at different rates). The output is a combined cleaned set of behavioural and imaging data that is written to the specified output file. Runtime: a few minutes (bottleneck is reading in .xslx files)

Program 2 (Place cell identification) takes as input the cleaned data from program 1, as specified by th einput pathway, and labels the cells in the Ca2+ data as either place cells or not place cells based on a comparison of their spatial information to the spatial information of shuffled data. Place cell identification is based on random shuffles, so it might not match exactly. Output is a table showing whether each cell is a place cell, written to the specified output file. Runtime: a few minutes (bottlenck is the shuffling operation)

Program 3 (cell activity - there are two versions, depending on whether 4 or 6 behavioural sessions are used) takes as input the cleaned data from program 1, as specified in the input pathway, and the place cell identification from program 2, determines the total per-session activity for each cell, and creates a combined table of the total activity and the place cell identification. The output is a table showing the place cell identifications for each cell and the cell activity per session, written to the specified output file. Runtime: less tha a minute

Program 4 (Gaussian smoothed ratemaps - there are two versions, depending on whether 4 or 6 behavioural sessions are used) takes as input the cleaned data from program 1 for all the sessions for a mouse, determines the rate maps for each cell, and performs Gaussian smoothing on the rate maps. The output is the smoothed and unsmoothed ratemaps for each cell for each session, written to the output pathways. Runtime: less than a minute 

Program 5 (there are two versions, depending on whether 4 or 6 behavioural sessions are used) takes as input the Gaussian smoothed rate maps for all the sessions for a mouse, and determines the session 1-3 correlations and session 2-4 correlations for each cell. It also plots the smoothed rate maps for a given cell. The output is the session 1-3 correlation and session 2-4 correlations for each cell of the mouse. Runtime: about a minute

Program 6 takes as input the rate maps for all the sessions for multiple mice, and determines the session 1-3 PV correlation and session 2-4 PV correlation across all mice. These PV correlations are compared to shuffled versions of the ratemaps to determine significance. Runtime: about a minute 

**Instructions**

For each program:

1.  Open in Juypter
2.  Replace the file pathways and file names for the input files with your locations
3.  Replace the output pathway and file name(s) with your desired locations
4.  Run program
