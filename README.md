A collection of useful documentation is available [here](useful_links.md).

## Prerequisites
* Python 3.6+ and packages `jinja2`, `pyyaml`, `f90ml` and the additional packages if using graphics scripts `scipy`, `matplotlib`, `pygrib`, `cartopy`, `pillow`
* Anaconda (optional)
* gcc and gfortran v9+
* Perl 5
* git v2.12+
* curl
* wget
* Lmod

The following is needed but the HPC-Stack can build if needed (I installed them manually).
* CMake v3.20+
* MPI implementation (I used OpenMPI while on Ubuntu. MPICH is also common)

## Setup steps.

First follow the [LMOD setup](lmod_setup.md).

Next follow the [hpc stack setup](hpc-stack-setup.md).

Finally follow the [ufs-srweather-app setup](ufs-srweather-app-setup.md).

For the setup instructions, note that Ubuntu and CentOS are level 3 systems, so every step will need to be followed. Checking the [level information list](https://github.com/ufs-community/ufs-srweather-app/wiki/Supported-Platforms-and-Compilers), it might be worth using a cloud instance of a level 1 system as they already have HPC-Stack/spack-stack installed and tested.

## Alternative setups

The documentations provide instructions for a singularity based setup. This is a container base setup similar to docker, but unlike docker, it doesn't need super user permissions other than installing singularity.

Instead of installing hpc-stack. It might be possible to use [spack-stack](https://github.com/JCSDA/spack-stack) to install libraries

## Links

There is [some useful documentation](useful_links.md).