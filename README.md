# dGPredictor

==================================
### Requirements:

1. Python 2.7
2. RDkit (http://www.rdkit.org/)
3. pandas (https://pandas.pydata.org/)
4. Scikit-learn (https://scikit-learn.org/stable/) - use command "pip install -U scikit-learn"
5. Streamlit==0.55.2 (https://streamlit.io/)- use command "pip install -U streamlit"
6. Component-contribution (https://pennstateoffice365-my.sharepoint.com/:f:/g/personal/vuu10_psu_edu/EvF9kttgsvlJnhAs1FDRWFcBu0obprfFFjrZKJbq-Yw5sw?e=dPHo2w)- save the folder inside dGPredictor 
7. Openbabel (https://anaconda.org/openbabel/openbabel) - run "conda install -c openbabel openbabel" for installation

==================================
### Running web-interface loacally using streamlit
- run "streamlit run ./streamlit/main.py"

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

