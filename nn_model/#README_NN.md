
This directory consists of two main files for training and loading NN models suggestively used in sequence:

1. Configure the NN constraints and train the model via [nn_model_train.py](nn_model_train.py).
2. Once the model is trained and saved, load it and analyze it in [nn_model_load.py](nn_model_load.py) with plotters from [nn_model_lib.py](nn_model_lib.py).

These two files uses functions from the library [nn_model_lib.py](nn_model_lib.py), which contains the networks, model classes, training loop and plotters. The file in turn calls upon [fix_ecm.py](fix_ecm.py) to generate fixed value ecm fit along with [Ue_GP_comsol.py](Ue_GP_comsol.py) and [Ue_GP_pybamm.py](Ue_GP_pybamm.py) to generate a equilibrium voltage function.

[Ue_run_comsol.txt](Ue_run_comsol.txt) is data from a OCV experiment run in Comsol and [Ue_run_pybamm.txt](Ue_run_pybamm.txt) is the corresponding data from pybamm generator in the directory [data_pybamm](../data_pybamm/).
