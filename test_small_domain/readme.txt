
1) Generate 3D mask data
Use submerge_mask.m to generate the mask data

The data file contains a number of 3D moving masks (i,j,k) which have velocity components (u,v,w) and acceleration components (ax ay aw) at different time. (i,j,k) are indices of mask points. The model reads those mask data and generates boundary conditions at the interface of fluid and the object. Interpolation will be performed to calculate (u,v,w) and (ax ay aw) between different time levels.  

The following example shows the data format. 
mask data
TIME
0.00
20   number of mask points
 i   j  k    u      v      w    ax    ay    aw
11  23 10  1.00  0.00  0.00  0.00  0.00  0.00
12  23 10  1.00  0.00  0.00  0.00  0.00  0.00
13  23 10  1.00  0.00  0.00  0.00  0.00  0.00
14  23 10  1.00  0.00  0.00  0.00  0.00  0.00
TIME
0.10
20   number of mask points
 i   j  k    u      v      w    ax    ay    aw
11  23 10  1.00  0.00  0.00  0.00  0.00  0.00
12  23 10  1.00  0.00  0.00  0.00  0.00  0.00
13  23 10  1.00  0.00  0.00  0.00  0.00  0.00
14  23 10  1.00  0.00  0.00  0.00  0.00  0.00

2) set up model
An example is shown in input.txt

  a)The model reads depth file  
    DEPTH_FILE = wave_flume.txt

    ignore DEPTH_FULL_FILE and set MainGridRatio = 1
    because AMR version is not available yet. 

  b)specify result folder
    RESULT_FOLDER = /Users/fengyanshi15/tmp3/

  c)give 3D mask file name
    MASK3D_FILE = mask3d_data.txt

  Other parameter settings are the same as the regular version of NHWAVE

3) compile the code using -DOBSTACLE











