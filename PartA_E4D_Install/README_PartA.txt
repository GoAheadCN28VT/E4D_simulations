Part A is E4D Installation on NERSC. If you want to apply for a NERSC account, please read the file 'AccountsAllocations-20190621.pdf' for instruction. Some commands are used to show the result screenshot. To make it run, please remember to run the first line to import the packages:

                                        'from IPython.display import Image'
                                        
The notebooks follow T.C. Johnson's (also E4D Author) instruction:  https://bitbucket.org/john775/e4d_dev/wiki/Home.

There are 7 installation steps:
  Step 1: Log in NERSC;
  Step 2: Clone the E4D Repository;
  Step 3: Compile E4D;
  Step 4: Compile bx;
  Step 5: Compile Triangle;
  Step 6: Compile Tetgen;
  Step 7: E4D Test.(Optional)

All the contents are seperated into two notebooks -- Part_A_E4D_Install_1.ipynb (Step 1 to Step 4) and Part_A_E4D_Install_2.ipynb (Step 5 to Step 7). (I seperate them because the size of one notebook is too big to upload)

**For Linux-faimilar-users: 
It is not necessary for you to read relevant notebooks because I include all the possible commands into the notebooks, even very basic operations. So they are verbose for you. You can just follow T.J.'s instruction, which is very clear and compact. I list some tips here:

(1) Once logging into NERSC account, swap programming environment to 'gnu' to use 'make' and 'gfortran':

                                        'module swap PrgEnv-intel PrgEnv-gnu'
                                        
Check module 'PrgEnv-gnu' and 'gcc' are loaded or not.
                                        
(2) NERSC does not support Mercurial module in CLE7. You may currently access the CLE6 modulefiles (including the mercurial module):

                                  'module use /global/common/cori_cle6/software/modulefiles'

However, please be aware that these built for CLE6 are not guaranteed to work under CLE7.
You may want to download and install Mercurial in some specific environment like conda environment for longer term use:

                                    https://www.mercurial-scm.org/wiki/Download#Using_conda

To solver that problem: Download the reposity directly using 'wget'.

(3) The steps 'Instruction for compiling px' is an alternative for 'compiling bx' and need 'sudo' priviledge (not allowed on NERSC). You can skip this step on NERSC.

(4) In the step 'Instruction for compiling bx', 'make install' requires 'su' priviledge, which is not allowed on NERSC. So you have to skip it on NERSC. One possible error caused by that:
   E4D can't call 'bx' for visulization -- 'libgfortran.so.15: cannot open shared object file: No such file or directory'.

To solve that problem:

   You can add the library path manually. For example, my library path:
   /global/project/projectdirs/m1800/E4D_20190818/e4d_dev/third_party/netcdf/liblib/.libs
   
   Add the library path into a 'bash' file for terminal or into 'jupyter-help.sh' described in PartB_Kernel_Customize for notebook.
   
(5) When you compile 'tetgen', the latest version is tetgen1.5.1 or later. However, the code to call 'tetgen' in E4D is for tetgen1.5.0. So maybe you will meet some problems like: there are negative flags in your node file and your surface refinement looks awkward. I uploaded a compressed file of tetgen1.5.0.

Also, I list the website used for package downloads here. You can also find it on T.J.'s website:
(1) T.J.'s Instruction and E4D website: https://bitbucket.org/john775/e4d_dev/wiki/Home
(2) PETSc: https://bitbucket.org/petsc/petsc
(3) netcdf library: http://www.unidata.ucar.edu/downloads/netcdf/index.jsp
(4) exodus: https://launchpad.net/ubuntu/+source/exodusii/6.02.dfsg.1-8build1
(5) triangle: https://www.cs.cmu.edu/~quake/triangle.html
(6) tetgen: http://wias-berlin.de/software/tetgen/download2.jsp

**For Linux-new-user: 
You can check the results of every step command. Please keep in mind, set the path according your own case. The path and directory name
shown in the notebook just work for the example case. The folder I installed E4D is '/global/project/projectdirs/m1800/E4D_20190818'. So change the path and directory name respectively. If you meet an error like 'No such file or directory', please check your path is right or not. 

This is the end of 'README_PartA.txt'. Thank you for your reading and I will add something I missed once I realized that. And if you find any problems or have any advice about my commands or anything else, please contact me: hongsheng.wang@pnnl.gov.