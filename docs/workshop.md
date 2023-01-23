# Hands-on Workshop January 23, 2023

Contact Megan Duff or Jan Mandel will be happy to answer any questions!

## Log in
* know your CU Denver username
* open a Terminal (mac), xterm (linux), or command/powershell (windows 10 or 11) 
* type into the window: *ssh username@math-alderaan.ucdenver.pvt* f
* Enter your CU Denver password
    
## Check out the command line
* The easiest text editor is *nano*, exit it by *control-x*
* *mkdir* to make a directory, *cd* to change directory. *cd ..* will go to the parent directory.
* *man commandname* to get help about a command. Try *man top*

## Get the templates
* Type *git clone https://github.com/ccmucdenver/templates* 
* Type *cd templates* and *ls* to see what files you have there 

## Submit a batch job
* Look at the file *alderaan_simple.sh*
* Submit it: *sbatch alderaan_simple.sh*
* Look for the output file, it will have name starting with *slurm* 
* Try a GPU job: *sbatch alderaan_single_gpu.sh*  What did it do? Look at the output.

## Using multiple CPUs at the same time
* Multiple cores within a single node - just put the number on the --ntasks or -n line other than 1 when using software that written to use multiple cores automatically, such as R or Matlab.
* Multiple cores on multiple nodes - we have 2048 cores total on the compute nodes! - you need to have a code specifically written for this. Let's build some. Type 
    cd examples
    make
* Look at *alderaan_single.sh* *alderaan_mpi_general.sh* and submit them

## Singularity containers
* Complete computing environments with custom software and different Linux versions.
* Our containers are in */storage/singularity*. See [Singularity](../singularity/) for what containers we have and more details.
* *alderaan_single_gpu.sh* you used before runs tensorflow in a singularity container. Look at the script how it works!
* *singularity_alderaan_shell.slurm* allows you to run an entire shell script in a singularity container. Try to add another command. Try to use another container.

## Interactive jobs
* Please do not ssh to work on compute nodes, you could interfere with jobs running there which would make you very unpopular. It is OK to ssh to compute nodes to check on your running jobs submitted through sbatch, however.
* The magical incantation
```
srun -p math-alderaan --time=2:00:0 -n 1 --pty bash -i
``` 
will teleport your session to a compute node for two hours with one core reserved for you. Try it! Your interactive job will not interfere with CPU usage of other. Try *matlab -nodesktop*, run something CPU intensive, and check by *top* from another terminal window. But you may interfere with memory use. Keep reading below.

## Memory
* Our compute nodes have 64 cores and 512GB memory each. We do not treat memory as allocatable resource yet, so if the processes running on a node try to use even close to the maximum, things will slow down.  If you want to use anywhere close to the full memory (512GB in the math-alderaan partition), grab the whole node (request -N=1 -n=64). But don't do that on the math-alderann-gpu partition with 2TB nodes, you would block the GPU use of others. If you need to use the 2TB memory, talk to us first.

Please see the 


