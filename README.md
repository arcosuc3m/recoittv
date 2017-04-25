# README #


### What is this repository for? ###
We present a new Surface-Constrained Total Variation based (SCTV) method for CBCT based on the Split Bregman algorithm. It takes advantage of the surface information of the sample as an imposed constraint to help in the recovery of the contour of the sample and in the definition of the other edges and details.
We provide binaries of a command-line application that implements the SCTV method. 


Current Version is 1.4.1. 


### Minimum Requirements ###

#### Hardware #####

* One NVidia GPU with CUDA support (preferably series 6 or superior).
* 20 GBytes of RAM (512^3 cubic volume reconstruction)*.

*The memory requirements depend on the size of input and output data. 

#### Software ####

* Linux system (x64 architecture) (Recommended: Ubuntu 14.04 or higher) or Windows system  (7 or higher) (x64 architecture).
* NVidia CUDA 8.0 or higher.
* Support for OpenMP.

### Set up ###

We provide the binaries for our application. You can install the files as they are in any folder in which you have execution permissions. 
Since it is a command line application it is necessary to use a command shell. 

* Windows: we recommend the usage of PowerShell
* Linux System: you can use your preferred shell. 




### Usage ###

Our application accepts the following parameters: 

-fi [string]	path to input file
-fo [string]	path to output file

-n  [int]	number of projections
-s  [float]	initial angle (deg)
-t  [int]	rotation direction
  -1 - counter-clockwise
   1 - clockwise (default)

-b  [int int int]	volume size in voxels
-r  [int int int]	VOI dimension in voxels
-o  [float float float]	VOI offset in voxels
-c  [float float float]	volume voxel size (mm)
-d  [int int]	projection size (pixels)
-e  [int int]	projection ROI size (pixels)
-g  [float float]	projection ROI offset (pixels)
-u  [float float]	projection pixel size (mm)
-p  [float]	detector-to-object distance (mm)
-q  [float]	source-to-object distance (mm)

-tv [5xfloat] TV3D parameters
  alpha
  mu
  beta
  lambda
  gamma
  retroNorm

-kr [float int]	Krylov solver parameters
  tolKrylov
  max_iterations

We provide you some samples to test the application, a test call could be: 

<recoit executable path> -fo .\recoTV -fi .\data_0 -a 360 -r 256 256 256 -b 256 256 256 -d 256 256 -n 90 -o 0 0 0 -u 0.2 0.2 -t -1 -c 0.12 0.12 0.12 -q 132 -p 220 -s 0 -h 1 0 0 0 0 0 -tv 0.0003 20 3 2 0 0.00390625 -i 2 -kr 1e-2 100

Please take into account that the calibration file provided and the data must be in the same directory.

### Citing SCTV ###

When citing this SCTV application you can use the following bibtex reference: 

TBA

### Disclaimer ###

The author makes no warranties about the usage of this application or any parts of its contents and accepts no responsibility for any data loss or other system trouble that may occur from its usage.

### Who do I talk to? ###

For doubts or problems related to the usage of this software you can contact the following e-mail address:
TBA
