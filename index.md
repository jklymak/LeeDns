---
layout: default
title: Home
---

# Preamble:

This is all done on `haise.navo.hpc.mil`
# 2-d Fine runs:

These are approx 4mx4m near the Gaussian bump, and telescope out away.  There are a few of them.  They use 128 cores.  They run at about 6x simulation time; i.e. 60 h can get done in 10 h of simulation time.  

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
The  
