# How to run the LyA Nyx code
The LyA test case in the [Nyx repo is here](https://github.com/AMReX-Astro/Nyx/tree/development/Exec/LyA)

1. Sample makefile for compiling Nyx is provided
```
make -j8
```
The dependencies are [Sundials](https://github.com/LLNL/sundials) (required), [Reeber](https://github.com/mrzv/reeber) (if halos are to be output), and [Ascent](https://github.com/Alpine-DAV/ascent) (if in-situ is needed). All the repositories are open-source.   
2. See the [CosmicIC directory](https://github.com/cosmo-suite/NyxCompilationAndRunning/tree/main/CosmicIC) for details of creating the initial condition.  
3. List the names of the initial condition files output by the CosmicIC code in a `FileList.txt`.    
4. Use the file list created in step 2 to initialize the run using the following options in the inputs.   
```
   nyx.particle_init_type = BinaryMetaFile
   nyx.binary_particle_file = FileList_2048.txt
```
The domain is specified using the inputs options
```
#Domain size in Mpc
geometry.prob_lo     =  0     0     0
geometry.prob_hi     =   237.037037037 237.037037037 237.037037037
```
Note that the units in Nyx is in Mpc, whereas the CosmicIC initial particle generation code is Mpc/h. So divide the value - ie. `box_size` in the `input.par` used for CosmicIC, to use as input for `prob_hi` for Nyx.  

The number of cells in each direction is specified using
```
amr.n_cell           =  2048  2048  2048
```
There are various other options. Look into the sample inputs file in the Nyx repo for the test case and refer to the [Nyx documentation](https://amrex-astro.github.io/Nyx/docs_html/) for details.


