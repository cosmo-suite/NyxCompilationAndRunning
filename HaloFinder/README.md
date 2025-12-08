# How to run the HaloFinder Nyx code

## How to run on Frontier
This is regarding running a large scale simulation of the Nyx code for lightcone shells and halo finding.

For a 8192^3 simulations, the reading of the initial condition files takes about 4.5 hours on Frontier GPUs.  
Hence, it is best to write a checkpoint file after reading the initial condition files for the first step.  
And then subsequent runs can be done with this.

This repo has the inputs file for writing the checkpoint file and then reading the checkpoint file in and running.  
The submission scripts are also provided
