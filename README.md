# Running Nyx simulations on Perlmutter and Frontier

This repositories contains the details of how to run simulations using [Nyx](https://github.com/AMReX-Astro/Nyx) - DOE's flagship code for 
cosmology. [Nyx](https://github.com/AMReX-Astro/Nyx) is an open-source code based on [AMReX](https://github.com/AMReX-Codes/amrex). 
The different test cases are in the [Exec](https://github.com/AMReX-Astro/Nyx/tree/development/Exec) directory. This repository 
contains some isntructions of how to run these test cases. Here is what the individual directories in this repository contain

1. `CosmicIC` - generating initial conditions for the dark matter particles. Required by all simulations.
2. `Gimlet` - post processing Nyx data
3. `HaloFinder` - writing lightcones and halos for dark matter simulations
4. `LyA` - Lyman alpha forest simulations.

These are not end-to-end details. But inputs, makefiles and scripts on Perlmutter and Frontier.
