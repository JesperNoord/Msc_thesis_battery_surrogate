
[data_pybamm.ipynb](data_pybamm.ipynb) calls functions in [sim_pybamm.py](sim_pybamm.py) and [exp_pybamm_ver4.py](exp_pybamm_ver4.py) to generate voltage trajectory data.

The file can save data in the format, with compression and force dummy values, that matches the data format used in the [nn_model](../nn_model) directory. It can also generate the [Ue_run_pybamm.txt](Ue_run_pybamm.txt) used in [nn_model](../nn_model). To do so use `get_Ue=True`.
