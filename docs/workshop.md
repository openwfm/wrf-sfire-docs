# Hands-on Workshop January 23, 2023

Contact Megan Duff or Jan Mandel will be happy to answer any questions!

## Log in
* know your CU Denver username
* open a Terminal (mac), xterm (linux), or command/powershell (windows 10 or 11) 
* type into the window: *ssh username@math-alderaan.ucdenver.pvt* f
* Enter your CU Denver password
    
## Check out the command line
* the easiest text editor is *nano*, exit by *control-x*
* *mkdir* to make a directory, *cd* to change directory. *cd ..* will go to the parent directory.
* *man commandname* to get help about a command. Try *man nano*

## Get the templates
* type *git clone https://github.com/ccmucdenver/templates* 
* type *cd templates* and *ls* to see what files you have there 

## Submit a batch job
* look at the file *alderaan_simple.sh*
* submit it: *sbatch alderaan_simple.sh*
* look for the output file, it will have name starting with *slurm* 
* try a GPU job: *sbatch alderaan_single_gpu.sh*  What did it do? Trace that.

## Using multiple CPUs at the same time
* Multiple cores within a single node - just put the number on the --ntasks or -n line other than 1 when using software that written to use multiple cores automatically, such as R or Matlab.
* Multiple cores on multiple nodes - we have 2048 cores total on the compute nodes! - you need to have a code specifically written for this. Let's build some. Type 
    cd examples
    make


