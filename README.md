# Explainable-Decision-Support-Lung-Cancer

This repository contains the code and trained pipelines from the paper "Development of an explainable clinical decision support tool for advanced lung cancer patients".


In the folder **code**, you can find two notebooks; training.ipynb and explainability.ipynb. The former guides you through training a pipeline with the preprocessing steps and models as discussed in the paper, the latter plots several Shapley plots. 

You can use these notebooks with your own data, training results will then be saved in **results**. A dummy patient is included to show how the data should look like in **data/dummy_data.csv**. Make sure that you use the correct columns for each model, you can see what columns were used in the trained pipelines with:

```python
columns = pipeline[:-1].get_feature_names_out()

print(columns)
```


The folder **pipelines** contains the pipelines (preprocessing + voting classifier) of which the results were mentioned in the paper. If you use these pipelines to run inference on your own data, please let us know your results. 

For questions or issues, use the **issues** section in the repository or contact louise.berteloot@azdelta.be. 

