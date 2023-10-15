# STC
**Python Data Pipeline for “Synaptic tagging and capture underlie neuronal co-allocation and temporal association memory in behaving mice” Paper Data Analysis**
**Written for Python in Jupyter** 


This set of programs processes raw Ca2+ imaging data and raw mouse behavioural data to: (i) identify place cells in the raw Ca2+ imaging data; (iii) determine rate maps for the activities of each cell in each session; and (iv) determine the correlations between rate maps across sessions. 

Program 1 (Interpolation) takes as input the raw Ca2+ imaging data (output by IDPS from Inscopix in .csv form) and the raw behavioral data (output by Ethovision in .xslx form), and cleans the data, including interpolating values of the behavioural data at the Ca2+ imaging times (as the Ca2+ data and behavioural data are sampled at different rates). 

Program 2 (Place cell identification) takes as input the cleaned data from program 1, and labels the cells in the Ca2+ data as either place cells or not place cells based on a comparison of their spatial information to the spatial information of shuffled data. Place cell identification is based on random shuffles, so it might not match exactly. Output is a tbale showing whether each cell is a place cell. 

Program 3 (cell activity - there are two versions, depending on whether 4 or 6 behavioural sessions are used) takes as input the cleaned data from program 1 and the place cell identification from program 2, determines the total per-session activity for each cell, and creates a combined table of the total activity and the place cell identification. The output is a table showing the place cell identifications for each cell and the cell activity per session. 

Program 4 (Gaussian smoothed ratemaps - there are two versions, depending on whether 4 or 6 behavioural sessions are used) takes as input the cleaned data from program 1 for all the sessions for a mouse, determines the rate maps for each cell, and performs Gaussian smoothing on the rate maps. The output is the smoothed and unsmoothed ratemaps for each cell for each session.  

Program 5 (there are two versions, depending on whether 4 or 6 behavioural sessions are used) takes as input the Gaussian smoothed rate maps for all the sessions for a mouse, and determines the session 1-3 correlation and session 2-4 correlation. It also plots the smoothed rate maps for a given cell. The outout is the session 1-3 correlation and session 2-4 correlations for each cell of the mouse. 

Program 6 takes as input the rate maps for all the sessions for multiple mice, and determines the session 1-3 PV correlation and session 2-4 PV correlation across all mice. These PV correlations are compared to shuffled versions of the ratemaps to determine significance. 
