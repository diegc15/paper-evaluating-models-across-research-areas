Simulations
================

This directory contains all scripts used to simulate systematic reviews:

  - `config` - contains the hyperparameters for every model-dataset
    combination. These files are called upon in the simulation command.
    They are copies from the config files in the `hpoptimization/config`
    directory, except that the `n_instances` parameter has been set to
    1, so that the model is retrained after labelling one publication
    instead of 20.
  - `scripts` - contains all scripts run on the Cartesius supercomputer.
  - `simoutput` - where the output of the simulation files is stored. As
    mentioned in the readme in the root directory, the files resulting
    from this simulation are enormous (over 500GB in total), therefore
    they cannot be stored on GitHub and the `simoutput` directory
    remains empty. Instead, the simulation output files are published on
    the Open Science Framework: <https://osf.io/7mr2g/> and
    <https://osf.io/ag2xp/>.

## Running a simulation

All simulations were run with seed value `42`. If you want to run a
simulation locally, for example the NB + TF-IDF model on the nudging
dataset, for 15 trials, run the following in your bash terminal:

``` bash
asreview batch ../../datasets/sim_datasets/nudging.csv --config_file config/one/BCTD/nb_max_double_tfidf-nudging.ini --state_file simoutput/one/BCTD/nudging/results.h5 -r 15 --init_seed 42
```

The simulation will output 15 `.h5` files. Please refer to the `results`
folder in the root directory of this repository for a demonstration of
how to analyze the resulting files. Code for processing these files can
be found in the `results` directory, which also contains already A
processed version of the simulation output files is available in the
`results` directory.
