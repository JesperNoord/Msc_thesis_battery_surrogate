The SR folder has five notebook files that needs to be run to obtain symbolic expressions, i.e.
- SR_run
- SR_run_Ue
- interpret_expr
- SR_global_outputs.
While these files have some internal functions, most of the functions are defined in SR_lib.

This is the workflow used for SR:
### Extract sample points from the `lhs_SR.py` file and save the samples in a .csv file
### Run the SR optimization (`SR_run.ipynb` & `SR_run_Ue.ipynb`)
- [SR_run.ipynb](SR_run.ipynb) runs SR for $R_0$, $R_1$, $C_1$, $k$, $\dot{s}$ based on what has been specified in the SR_lib file for the SR. 
    - Before running, optimization settings can be changed in the `SR_lib.py` file. 
- Start by defining a new `run_id` in [SR_run.ipynb](SR_run.ipynb).
- Import the samples that were saved and run the file. 
- Save the extracted expressions. 
- Extract expressions for $U_{eq}$. 
    - The same `run_id` needs to be used for finding $U_{eq}(\mathrm{SOC})$. Finding expressions is done in (SR_run_Ue.ipynb)[SR_run_Ue.ipynb].
### Interpret the expressions and choose which to save (`interpret_expr.ipynb`). 
- This is done in the [interpret_expr.ipynb](interpret_expr.ipynb) file
-  Start with specifying the `run_id` you want to look at. 
- Compare the loss-to-complexity plot (Pareto frontier), and **save two** expressions. 
	- We saved a simpler and a more complex expression that were compared. 
	-  **Saving** is done be writing the expressions' index in the [best_indices.csv](saved_sr_models/best_indices.csv) and [chosen_indices.csv](saved_sr_models/chosen_indices.csv) files, where the **best** refer to the **high complexity** and the **chosen** has **lower complexity**. 
### Include the SR expressions in a full solver and solve for the observed/global outputs (`SR_global_outputs.ipynb`). 

- This is done in [SR_global_outputs.ipynb](SR_global_outputs.ipynb)

- The main function here is `solve_multi_physics`, where one can specify what should be solved for. 

    - It also offers the ability to simulate the global outputs with the NNs instead of the SR expressions. 

- There are various plotting functions in this file. **For instance**, the extrapolation plot can be found here. 
### Examine the NN outputs in more detail.
 [plot_elements.ipynb](plot_elements.ipynb) also has various plotting options. For instance, a plot for comparing the NN predictions to the SR expressions. 