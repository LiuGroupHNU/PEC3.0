# title
PEC3.0

## Installation
Download the executable file.

## Useage
Various command prompts:
   --infile,          Input file，GDSII layout to be corrected；
   --outfile,       Output file，Corrected GDSII layout；
   --psf,             Point spread function，At present, only the double Gaussian form is supported, and the order of the four parameters is K, eta, alpha, beta, and beta is the largest of all parameters.；
   --struct,          GDSII layout structure to be corrected；
   --layer,           GDSII layout layer to be corrected；
   --min_quad_mesh,   The smaller the mesh, the higher the accuracy, but the longer the calculation time. 1/2 of the critical dimension is recommended；
   --max_quad_mesh,   Maximum mesh for fracturing,do not exceed 255；
   --threads,         Number of OpenMP parallel threads；
   --threshold,       Development threshold；
   --dose_iter,       Number of iterations for dose correction，usually 5 times；
   --shape_iter,      Number of iterations for shape correction.The greater the number of iterations, the longer the computation times；
   --max_avail_epe,   Maximum acceptable edge placement error;
   --export_gds,	Whether to export GDSII file,Defaults to 0 (no output).
   
   Note that these are long parameters, which can be used in the following ways:
   	1. --infile=test.gds
   	2. --infile test.gds
   The test folder contains a number of Manhattan maps that we have tested, and you can also test with maps that meet your requirements.
The data folder contains the effect pictures of some results after the test. After the test, you can visualize the effect before and after PEC through the output exposure file.


# Run the sample
./pec --infile 1um_1um.dgs --struct 1mm_1mm --layer 31 --export 1


## Test layout limitations
- Manhattan layout, that is, the edges of the polygon in the layout are horizontal or vertical.；
- Single-layer single-structure layout, and no overlapping of polygons；
- Layout area is less than 2mm×2mm.

## Environment configuration requirements
(1) GCC version 9.4.0 (Ubuntu 9.4.0-1ubuntu1~20.04.2) 
(2) GNU Make 4.2.1 
(3) GSL version 2.5 
(4) Boost version 1.71.0 
(5) FFTW3.3.10
(6) OpenMP 4.5


## Function
1. Manhattan layout mask fracturing
2. Electron beam simulation to calculate proximity effect
3. Proximity effect correction
4. Calculation of edge placement error
5. Output fracturing GDSII layout

## R&D team
R&D Team (School of Electrical and Information Engineering, Hunan University&School of Integrated Circuits, Hunan University): Jie Liu, Haojie Zhao, Siyuan Zhang, Yujie Yang, Jiaxin Chen, Xiaoyang Zhong, Hongyi Zeng, Yupeng Wei
Experiment R&D Team (School of Mechanical and Transportation Engineering, Hunan University)：Huigao Duan, Yiqin Chen, Jian Zhou
Homepage ：http://www.ebeam.com.cn/


## Contact us
We are open to collaborations on EBL simulation and optimization, EBL EDA tool development, etc. Feel free to email us if you are interested in collaborating with us.
We are currently engaged in the deployment of PEC3.0 functionality to the HNU-EBL software. Feel free to email us, if you have any question/suggestion:
jie_liu@hnu.edu.cn
support@ebeam.com.cn
