# Coding

## 1. EDA

| Index | Filename                      | Description                                                         |
|-------|-------------------------------|---------------------------------------------------------------------|
| 1 | BTC time series.ipynb | Get BTC data and squared demeaned log returns | 
| 2 | BTC EDA.ipynb | Elvis: EDA of BTC data |
| 3 | BTC GARCH.ipynb | Plot the conditional volatility |

## 2. List of functions: Your own defined functions 



| Index | Function                      | Description                                                         |
|-------|-------------------------------|---------------------------------------------------------------------|
| 16    | `load_real_data`              | Load the `coinPrice.csv` file                                        |
| 1     | `APE = calc_APE`              | Calculate APE (Absolute Percentage Error)                           |
| 2     | `create_folder`               | Create the folder “model_T_N” and save the param and update_flag in the filename_mat (mcmc_result) |
| 3     | `update = define_flag(model)` | Decide the update flags for each model                              |
| 4     | `param = define_param`        | Define true parameters                                              |
| 5     | `generate_BS_return(param, num_paths)` | Generate return for BS model                                    |
| 6     | `generate_SV_return(param, num_paths)` | Generate return for SV model                                    |
| 7     | `generate_SVJ_return(param, num_paths)` | Generate return for SVJ model                                   |
| 8     | `generate_SVCJ_return(param, num_paths)` | Generate return for SVCJ model                                  |
| 9     | `Param = run_mcmc(param, data)` | Run MCMC with the data, output results, and save figures          |
| 10    | `save_figure`                 | Save 11 trace plots in the “model_T_N” folder.                      |
| 11 | `gen_GARCH.m` | generate paths from GARCH(1,1) model with a constant mean. Usage [Y, V] = gen_GARCH(control, param) | 
| 12 | `estimate_GARCH.m` | Estimate parameters under the GARCH(1,1) model with a constant mean using matlab built-in function. Usage [est_mu, est_omega, est_alpha, est_beta, Ehat, Vhat, z] = estimate_GARCH(Y) | 

## 3. Test files: Use to generate benchmark outputs

| Index | Function                      | Description                                                         |
|-------|-------------------------------|---------------------------------------------------------------------|
| 1? | `test_BS.m`                   | Test file to check if BS model works. Teng 20250910: Inconsistent subfiles?                           |
| 2     | `test_SV.m`                   | Test file to check if SV model works                                |
| 3     | `test_SVJ.m`                  | Test file to check if SVJ model works                               |
| 4     | `test_SVCJ.m`                 | Test file to check if SVCJ model works                              |
| 6     | `test_whole_data_param`       | Load real data finding estimated param for different models. This is the DEMO file.    |
| 7 | `test_GARCH.m`                    | Generate GARCH model using `gen_GARCH.m`, estimate it with matlab built-in funciton.| 
| 8 | `test_GARCH_from_scratch.m`      | Generate GARCH model from scratch, estimate it with matlab built-in funciton.|
| 9 | `test_GARCH_matlab_builtin.m`  | Generate GARCH model using matlab built-in funcitons, estimate it with matlab built-in funciton.|


## 4. Test files: Analyzing the whole dataset using rolling window

| Index | Filename                  | Description                                                                                              |
|-------|---------------------------|----------------------------------------------------------------------------------------------------------|
| 1  * (TENG)  | `test_run_mcmc.m`         | Estimate parameters; Save parameters (estimated by mcmc) of every window data to .mat file                                                        |
| 2  *   (TENG)| `test_calc_VaR_ES.m`      | Read the mat file created by ‘test_run_mcmc.m’; calc VaR, ES and save in .csv file. input: “BS_H30_N1000_mcmc_outputs/mcmc_estimates_20181031.mat”, output: “BS_H30_T1_results.csv”,Produce VaR_ES_alpha0.05.cs  |
| 3     | `VaR_ES_figure.m`         | Save tranparent time series                                                                              |
| 4  * | `backtest_VaR.m`          | Read the csv file created by ‘test_calc_VaR_ES.m’, calc traffic light, independence and save in .csv file. |
| 5  *  | `backtest_ES`             | Read the csv file created by ‘test_calc_VaR_ES.m’, calc Z1, Z2, Z3 test and save in .csv file            |
| 6     | `summary_VaR_table`       | By setting values for H and alpha, organize the VaR table for different h and models; input: “BS_H30_T1_results.csv”, output = VaR_ES_Alpha0.05.csv?  |
| 5     | `summary_ES_table`        | By setting values for H and alpha, organize the ES table for different h and models; ; input: “BS_H30_T1_results.csv”, output = VaR_ES_Alpha0.05.csv? |


## 5. Summary files

| Index | Function                      | Description                                                         |
|-------|-------------------------------|---------------------------------------------------------------------|
| 11    | `summary_table_APE`           | Create table in `folder_to_save`. See thesis table 3.1.                                      |
| 12    | `summary_BS_table_APE`        | Create pivot table for BS model. See thesis table 3.2.        |
| 13    | `summary_SV_table_APE`        | Create pivot table for SV model. See thesis table 3.3.                                       |
| 14    | `summary_SVJ_table_APE`       | Create pivot table for SVJ model. See thesis table 3.4.                                      |
| 15    | `summary_SVCJ_table_APE`      | Create pivot table for SVCJ model. See thesis table 3.5.                                     |
| 18    | `summary_figure_VaR`          | Calculate numbers below VaR and save the plot. See thesis table 3.6.                        |

