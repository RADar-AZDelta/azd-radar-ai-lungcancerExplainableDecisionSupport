# Explainable-Decision-Support-Lung-Cancer


This repository contains the code and trained pipelines from the abstract https://www.jto.org/article/S1556-0864(23)00466-5/fulltext and the submitted paper "Development of an explainable clinical decision support tool for advanced lung cancer patients" (not yet accepted nor published).

Models
======

This repository contains six trained pipelines with pre-processing steps and binary classification models included (see pipelines/). Pre-processing steps are one hot encoding for the categorical features and robust scaling for the continuous features. Unbalanced datasets are handled with Synthetic Minority Oversampling TEchnique (SMOTE). All models are soft voting classifiers (ensembles) with five base estimators: logistic regression, knearest neighbors classifier, random forest classifier, xgboost classifier and support vector machine.

Following questions are being addressed with the six models:

1. Will the patient die within six weeks after baseline? (no/yes)

    M_6weeks_30_feats_v2.pkl
2. Will the patient die between six weeks and three months after baseline? (no/yes)

    M_3months_34_feats_v2.pkl
3. Will the patient die between three months and six months after baseline? (no/yes)

    M_6months_38_feats_v2.pkl
4. Will the patient die between six months and one year after baseline? (no/yes)

    M_1year_42_feats_v2.pkl
5. How will the alopecia of the patient evolve within five to nine weeks after baseline? (no change/negatively)

    alopecia_6_feats_v1.pkl
6. How will the dysphagia of the patient evolve within five to nine weeks after baseline? (no change/negatively)

    dysphagia_7_feats_v1.pkl






Notes on use
=======

**Pre-requisites**: 
- python version 3.10
- jupyter notebook 

Install the correct versions of the packages.

With pip:

````bash
pip install -r requirements.txt
````
*OR* 


With with pipenv:
```bash
pipenv install 
````


In the folder **code**, you can find two notebooks; training.ipynb and explainability.ipynb. The former guides you through training a pipeline with the preprocessing steps and models as discussed in the paper, the latter plots several Shapley plots. 

You can use these notebooks with your own data, training results will then be saved in **results**. A dummy patient is included to show how the data should look like in **data/dummy_data.csv**. Make sure that you use the correct columns for each model, you can see what columns were used in the trained pipelines with:

```python
columns = pipeline[:-1].get_feature_names_out()

print(columns)
```


The folder **pipelines** contains the pipelines (preprocessing + voting classifier) of which the results were mentioned in the paper. If you use these pipelines to run inference on your own data, please let us know your results. 

For questions or issues, use the **issues** section in the repository or contact louise.berteloot@azdelta.be. 


Authors
======

[Berteloot Louise](https://github.com/lbertelo01)

[De Jaeger Peter](https://github.com/peterdejaeger)

License
=======

Copyright © 2022, [RADar-AZDelta](mailto:radar@azdelta.be).

Released under the [GNU General Public License v3.0](LICENSE).
