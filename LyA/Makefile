# AMREX_HOME defines the directory in which we will find all the AMReX code
AMREX_HOME ?= ../../subprojects/amrex
# TOP defines the directory in which we will find Source, Exec, etc
TOP = ../..
COMMON_DIR = /global/common/software/nyx/nataraj2
#ASCENT_HOME ?=  ${CURDIR}/$(TOP)/../ascent/install-debug
ASCENT_HOME ?=  ${COMMON_DIR}/ascent/install-debug
# compilation options
COMP    = gnu
USE_MPI = TRUE
# Use with Async IO
MPI_THREAD_MULTIPLE = FALSE
USE_OMP = FALSE
USE_CUDA = TRUE
USE_SUNDIALS      = TRUE
USE_FORT_ODE = FALSE
#SUNDIALS_ROOT ?=  ${CURDIR}/$(TOP)/../sundials/instdir
SUNDIALS_ROOT ?= /global/cfs/cdirs/nyx/nataraj2/sundials_shared/sundials/instdir
PROFILE       = FALSE
TRACE_PROFILE = FALSE
COMM_PROFILE  = FALSE
TINY_PROFILE  = FALSE
PRECISION = DOUBLE
USE_SINGLE_PRECISION_PARTICLES = FALSE
DEBUG     = FALSE
USE_ASCENT_INSITU = TRUE
ifeq ($(USE_ASCENT_INSITU),TRUE)
  ASCENT_HOME ?= NOT_SET
  ifneq ($(ASCENT_HOME),NOT_SET)
    include $(ASCENT_HOME)/share/ascent/ascent_config.mk
  endif
  USE_CONDUIT = TRUE
  USE_ASCENT = TRUE
endif
# physics
DIM      = 3
USE_HEATCOOL = TRUE
USE_SAVE_REACT = FALSE
USE_AGN = FALSE
USE_RAYTRACING = TRUE
ifeq ($(NO_HYDRO),TRUE)
USE_SDC = FALSE
USE_SUNDIALS = FALSE
USE_FUSED = FALSE
else
ifeq ($(USE_HEATCOOL),TRUE)
USE_SDC = TRUE
USE_SUNDIALS = TRUE
ifeq ($(USE_HIP),TRUE)
USE_FUSED ?= $(USE_HIP)
endif
USE_FUSED ?= $(USE_CUDA)
else
USE_SDC = FALSE
USE_SUNDIALS = FALSE
USE_FUSED = FALSE
endif
endif
USE_CONST_SPECIES = TRUE
NEUTRINO_PARTICLES = FALSE
NEUTRINO_DARK_PARTICLES = FALSE
USE_OWN_BCS = FALSE
# Halo finder
BOOST_INLUDE_DIR := /usr/include/boost
REEBER = FALSE
DIY_INCLUDE_DIR =  /global/common/software/nyx/nataraj2/diy/include
REEBER_EXT_HOME = /global/common/software/nyx/nataraj2/reeber
Bpack := ./Make.package
Blocs := .
include $(TOP)/Exec/Make.Nyx
