# dGPredictor

==================================
### Requirements:

1. Python 2.7
2. RDkit (http://www.rdkit.org/)
3. pandas (https://pandas.pydata.org/)
4. matplotlib (https://matplotlib.org/stable/users/installing.html)
5. Scikit-learn (https://scikit-learn.org/stable/)
6. Streamlit==0.55.2 (https://streamlit.io/)
7. Component-contribution (https://pennstateoffice365-my.sharepoint.com/:f:/g/personal/vuu10_psu_edu/EvF9kttgsvlJnhAs1FDRWFcBu0obprfFFjrZKJbq-Yw5sw?e=dPHo2w)
8. Openbabel (https://anaconda.org/openbabel/openbabel)
9. ChemAxon's Marvin >= 5.11 

Installing on windows 
1. Python 2.7 (https://www.python.org/downloads/release/python-2718/)
Recommended- 
- Create anaconda environment using command "conda create -n dGPredictor python=2.7"
- activate the env using command "conda activate dGPredictor" or "source activate dGPredictor"
2. RDkit
- type command "conda install -c conda-forge rdkit" in your dGPredictor env to install rdkit
3. Pandas
- "conda install pandas"
4. matplotlib
- "conda install -c conda-forge matplotlib"
5. Scikit-learn
- use command "pip install -U scikit-learn"
6. Streamlit 
- use command "pip install -U streamlit"
7. Component-contribution
- download the package folder using the link provided
- save the folder inside dGPredictor (delete the empty component-contribution folder)
8. Openbabel
- run "conda install -c conda-forge openbabel" 
9. ChemAxon's Marvin (Component-contribution use this to estimate PkA values)
- Marvin is only required for adding structures of novel metabolites/compounds that are not in the KEGG database
- instructions (https://chemaxon.com/products/marvin/download)
- add cxcalc.bat to PATH
- you will need to get a license to use ChemAxon (it is free for academic use)



==================================
### Running web-interface loacally using streamlit

- Generate model file by "running model_gen.py" using "python model_gen.py" 
- run "streamlit run ./streamlit/main.py" from dGPredictor folder
- running KEGG reaction (doesn't require ChemAxon's Marvin) : copy paste the reaction equation into reaction section and click search

### Gibbs free energy prediction use automated group decomposition method

- Step 1: decompose the metabolites based on smiles files (see function decompse_ac in decompose_groups.py or notebook )
- Step 2: create group changes vectors (i.e. reaction rules) based on group changes in metabolites of reactions (see get_rxn_rule om decompose_groups.py)
- Step 3: cross validation to check model accuracy (note that for experimental replicates, we take the median value of measurements of the same chemical reaction in
different conditions or by different researchers)
- Step 4: linear regression, Ridge Regression and Bayesian Ridge Regression in "predict.py"
- Step 5: Multiple regression models in notebook "analysis_dGPredictor.ipynb"

### Pathway design using novoStoic
- See "mini_novoStoic.py"


# demo
![dGPredictor Demo](figures/dg_demo.gif)

