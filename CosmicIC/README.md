# Generate initial conditions for Nyx using the CosmicIC repo
This CosmicIC repo generates initial dark matter particle positions consistent 
with the overdenisty spectrum at a specified redshift. The transfer function used to 
generate the spectrum is in a file `cmb.tf` in the repo. The input file specifies all the 
required parameters for generating the initial particle locations. It runs in parallel 
using MPI. The steps are as below.

Dependenices: fftw library
 
1. git clone https://maheshnatarajan@bitbucket.org/zarija/cosmicic.git
2. cd cosmicic
3. make -j8
4. `mpirun -n <nranks> ./init input_128.par cmb.tf IC_File`

`IC_File` is the prefix to the filenames generated. Each rank writes the data into a 
separate file. These files can be read in by Nyx.
