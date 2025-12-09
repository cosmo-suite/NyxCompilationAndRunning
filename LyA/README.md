# How to run the LyA Nyx code
The LyA test case in the [Nyx repo is here](https://github.com/AMReX-Astro/Nyx/tree/development/Exec/LyA)

1. Sample makefile for compiling Nyx is provided
```
make -j8
```
The dependencies are [Sundials](https://github.com/LLNL/sundials) (required), [Reeber](https://github.com/mrzv/reeber) (if halos are to be output), and [Ascent](https://github.com/Alpine-DAV/ascent) (if in-situ is needed).  
2. See the [CosmicIC directory](https://github.com/cosmo-suite/NyxCompilationAndRunning/tree/main/CosmicIC) for details of creating the initial condition.  
3. List the names of the initial condition files output by the CosmicIC code in a `FileList.txt`.    
4. Use the file list created in step 2 to initialize the run using the following options in the inputs.   
```
   nyx.particle_init_type = BinaryMetaFile
   nyx.binary_particle_file = FileList_2048.txt
```



