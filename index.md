---
layout: default
title: Home
---

# Preamble:

This is all done on `haise.navo.hpc.mil`

[Runs](Runs/)


# 2-d Fine runs:


These are approx 4mx4m near the Gaussian bump, and telescope out away.  There are a few of them.  They use 128 cores.  They run at about 6x simulation time; i.e. 60 h can get done in 10 h of simulation time.  

  - `fine07`: standard run with a bit of bottom roughness: Archived! `fine07_files.tar.gz`; Stored 
  - `fine08`: stanradr run, but considerably rougher. The goal here is to break up the laminar boundary layer that is probably aphysical *without* resorting to higher Reynold's number


## workflow:

  1. edit `gendata.py` and run; remember to run `~/loadpython.sh` first to get all the modules loaded.
  2. edit `data`; `data.obc`;
  3. to run, edit `runModel.sh` and then `qsub runModel.sh`
  3. when run: `python/getSlices.py` gets complete slices.
  4. `python/getEnergy.py` gets an energy budget from the data.  Runs quicker than slices because the data is far smaller.
  5. Run something like `rsync -av /scr/jklymak/scratch/fine03/ hornby.seos.uvic.ca:LeeDns14/twoDfine/fine03/` to send back to `hornby.soes.uvic.ca`
  6. On `hornby` run ipython notebook in `/Users/jklymak/LeeDns14/twoDcoarse/ProcessCoarse.ipynb` (so far)
  
## Commentary:

### 9 Nov 2014: 
There is a relatively large difference in the `coarse` and `fine` barotropic energies.  I expect this is because they are different sized geometries.  Running `fine04` right now and if that is OK< I'll make a coarse run w/ exactly the same x limits and boundary forcing. OK, the real difference: the boundary conditions had the time wrap-around problem again.  I find that *very* annoying!   `fine05` seems to fix this.  The other `fine*` runs are basically junk at this point.

# 3-D fine run(s):

## Workflow

Is as above, but the inital data is taken from `fine07` run.

