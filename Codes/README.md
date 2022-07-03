## **Codes/** ##
All codes used to generate all datasets and images can be found in this directory.
### **Dependencies** ###
pandas                    1.4.2 <br/>
numpy                     1.22.3 <br/>
numpy-base                1.22.3 <br/>
matplotlib                3.5.1 <br/>
matplotlib-base           3.5.1 <br/>
scipy                     1.7.3 <br/>
statsmodels               0.13.2 <br/>
### **COWAVE_gen.py** ###
Contains the code used to generate "COWAVE.csv". Three functions are present: labeller_1(), labeller_2() and feature_gen(). labeller_1() takes a .csv file in the format of the WHO dataset. This dataset can be obtainied directly from the WHO website, or can be the dataset present in the "Data/" directory (if attempting to replicate the results). This function generates the "COVID19_Dataset_v1.csv" file.

labeller_2() and feature_gen() take the output of the labeller_1() function as their input. labeller_2() generates the "COVID19_Dataset_v2.csv" file. feature_gen() generates the "COWAVE.csv" file. The "COVID19_Dataset_v3.csv" file can be generated by modifying this function to stop and return after decomposing the time series (line 334).
### **GraphGen_Defx.py** (x = 1, 2, 3) ###
These files are used to generate the graphs for their corresponding definitions, as outlined in the accompaying paper (i.e., GraphGen_Def1.py was used to generate the graphs for Definition 1, etc). The list of countries for which the plots are made can be changed by changing the "countrylist" list in "GraphGen_Def1.py" and "GraphGen_Def3.py" and the "x" variable in "GraphGen_Def2.py" to the required country code(s), in the WHO dataset format.
### **svm.py** and **svm.ipynb** ###
File used to generate the baseline classifer metrics in "Table 1" in the corresponding paper.
### **xgb_bayesopt.py** and **XGB_BayesOpt.ipynb** ###
File used to generate the improved and final classifiers, and their metrics in "Table 2", "Table 3, "Table 6, and, "Table 8". The hyperparameter tuning can be performed using Bayesian Optimization (from the package at https://github.com/fmfn/BayesianOptimization) or using RandomSearchCV. All tuning was performed using Bayesian Optimization. The hyperparameter space searched in the paper is also given in this file.