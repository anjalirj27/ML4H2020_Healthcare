ML4H2020
==============================

Repository for projects of the ETH Zürich course "Machine Learning for Health Care (Spring 2020)" ([lecture page](https://bmi.inf.ethz.ch/teaching/261-5120-00l-machine-learning-for-health-care-spring-2020/)).

**Authors** :  
Pezz


## Project 1 - ECG Time Series
Classifying ECG signals of the [MIT-BIH Arrhythmia Dataset](https://www.physionet.org/physiobank/database/mitdb/) and the [PTB Diagnostic ECG Database](https://www.physionet.org/physiobank/database/ptbdb/) by Recurrent Neural Networks and make use of Transfer Learning techniques in order to improve predictive performance.

**Results**

|Models          |MIT-BIH<sup>*</sup>|PTBDB<sup>*</sup>|PTBDB<sup>°</sup>|PTBDB<sup>&dagger;</sup>|
|--------|:-----------:|:-----:|:------:|:---:|
|LSTM + FC    |F1: 0.184<br>Acc: 0.823|F1: 0.787 Acc: 0.776<br>AUROC: 0.808 AUPRC: 0.934|F1: 0.419 Acc: 0.722<br>AUROC: 0.5 AUPRC: 0.861|F1: 0.371 Acc: 0.565<br>AUROC: 0.397 AUPRC: 0.805|
|CNN + LSTM + FC |F1: 0.868<br>Acc: 0.971|F1: 0.940 Acc: 0.951<br>AUROC: 0.947 AUPRC: 0.982|F1: **0.988** Acc: **0.990**<br>AUROC: **0.988** AUPRC: **0.996**|F1: 0.992 Acc: **0.994**<br>AUROC: **0.990** AUPRC: **0.996**|
|LSTM + XGB<sup>&Dagger;</sup> |F1: 0.875<br>Acc: 0.976|F1: 0.971 Acc: 0.977<br>AUROC: 0.968 AUPRC: 0.988|F1: 0.963 Acc: 0.970<br>AUROC: 0.955 AUPRC: 0.983| - |
|CNN + LSTM + XGB<sup>&Dagger;</sup>|F1: **0.916**<br>Acc: **0.985**|F1: 0.983 Acc: **0.986**<br>AUROC: **0.980** AUPRC: **0.993**|F1: 0.981 Acc: **0.990**<br>AUROC: 0.977 AUPRC: 0.991|-|
|XGB|F1: 0.896<br>Acc: 0.979|F1: 0.970 Acc: 0.976<br>AUROC: 0.966 AUPRC: 0.987| - | - |
|Kachuee, et al.[1]|Acc: 0.934| - |F1: 0.951<br>Acc: 0.959| - |
|Baseline[2]|F1: 0.915<br>Acc: **0.985**|F1: **0.988**<br>Acc: 0.983|F1: 0.969<br>Acc: 0.956|F1: **0.994**<br>Acc: 0.992|

<sup>*</sup> Only trained on this dataset  
<sup>°</sup> Transfer Learning, pre-trained model trained on MIT-BIH, retrained with **frozen** base layers  
<sup>&dagger;</sup> Transfer Learning, pre-trained model trained on MIT-BIH, retrained with **unfrozen** base layers  
<sup>&Dagger;</sup> Base layers always frozen to train XGBoost

**Visualization of learned embeddings**
<center>

||t-SNE|UMAP|PCA|  
|:---:|:---:|:---:|:---:|  
|**MIT-BIH**|<img src="ECG-time-series/visualization/mitbih-tsne-50.png?" width="200">|<img src="ECG-time-series/visualization/mitbih-umap.png?" width="200">|<img src="ECG-time-series/visualization/mitbih-pca.png?" width="200">|
|**PTBDB**|<img src="ECG-time-series/visualization/ptbdb-tsne-50.png?" width="200">|<img src="ECG-time-series/visualization/ptbdb-umap.png?" width="200">|<img src="ECG-time-series/visualization/ptbdb-pca.png?" width="200">|

</center>

For more details about the project have a look at the `README.md` in the project directory `/ECG-time-series`.

## Project 2 - Diabetes Readmission Prediction

Investigating which medical features from patient records (categorical, numerical and text) play an important role in the prediction of patient readmission. Comparing models using only numerical + categorical features, only text and both.  

**Results**

<center>

|Cat./Num. Features|
|---|
|<img src="./Diabetes-readmission/visualization/num-cat-feature-importance.png" width="700">|

</center>

<center>

|Text Features|
|---|
|<img src="./Diabetes-readmission/visualization/text-feature-importance.png" width="700">|

</center>

For more details about the project have a look at the `README.md` in the project directory `/Diabetes-readmission`.

## Project 3 - Medical Image Segmentation

Using the U-Net neural network model [4] to segment MRI prostate images from the [NCI-ISBI 2013 Challenge - Automated Segmentation of Prostate Structures](https://wiki.cancerimagingarchive.net/display/Public/NCI-ISBI+2013+Challenge+-+Automated+Segmentation+of+Prostate+Structures) into anatomical regions (Peripheral Zone & Central Gland). Part of the project was to perform hyperparameter-tuning and try different optimizers and loss-functions to reduce generalization error.

**Results**

<center>

|Example Test Image and Prediction|
|:---:|
|<p align="center"><img src="./Image-segmentation/visualization/example.png" alt = "Test set example" width="600"></p>|
|<p align="center"><img src="./Image-segmentation/visualization/rot-example.png?" alt="Rotated test set example" width="600"></p>|

</center>

For more details about the project have a look at the `README.md` in the project directory `/Image-segmentation`.

## Project 4 - Splice Site Prediction
Splice site prediction is common problem in computational genome finding where it is desirable to find the splice sites that mark the boundaries of <i>exons</i> and <i>introns</i> in organisms whose cells have a nucleus enclosed within membranes (eukaryotes). This classification can then be used to predict a gene's structure, function, interaction or its role in a disease. Main challenge of this task was the high class imbalance of the splice sites.

**Results**

<center>

|C.Elegans DNA|
|:---:|
| <p align="center"><img src="./Splice-site-prediction/visualization/AUC-celegans.png?" alt="AUC c.elegans dna" width="500"></p> |

|Human DNA|
|:---:|
|<p align="center"><img src="./Splice-site-prediction/visualization/AUC-human.png?" alt="AUC human dna" width="500"></p>|

</center>

For more details about the project have a look at the `README.md` in the project directory `/Splice-site-prediction`.

### Requirements  
pandas, numpy, scikit-learn, keras, matplotlib, xgboost, umap-learn, seaborn, keras-contrib, tensorflow-addons

### References

[1] Mohammad Kachuee, Shayan Fazeli, and Majid Sarrafzadeh. "ECG Heartbeat Classification: A Deep Transferable Representation." [arXiv preprint arXiv:1805.00794 (2018) ](https://arxiv.org/abs/1805.00794).

[2] CVxTz's GitHub implementation: ECG_Heartbeat_Classification ([link](https://github.com/CVxTz/ECG_Heartbeat_Classification))

[3] Impact of HbA1c Measurement on Hospital Readmission Rates: Analysis of 70,000 Clinical Database Patient Records. [https://doi.org/10.1155/2014/781670](https://doi.org/10.1155/2014/781670)

[4] Ronneberger, Olaf & Fischer, Philipp & Brox, Thomas. (2015). U-Net: Convolutional Networks for Biomedical Image Segmentation. LNCS. 9351. 234-241. 10.1007/978-3-319-24574-4_28.

Project Organization
------------
For this repository the cookiecuter data science project template is used slightly adapted to the our needs and requirements. Each of the four projects is in a separate folder which is a copy of the `src` directory.

    ├── LICENSE
    ├── Makefile           <- Makefile with commands like `make data` or `make train`
    ├── README.md          <- The top-level README for developers using this project.
    ├── data
    │   ├── external       <- Data from third party sources.
    │   ├── interim        <- Intermediate data that has been transformed.
    │   ├── processed      <- The final, canonical data sets for modeling.
    │   └── raw            <- The original, immutable data dump.
    │
    ├── docs               <- A default Sphinx project; see sphinx-doc.org for details
    │
    ├── models             <- Trained and serialized models, model predictions, or model summaries
    │
    ├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
    │                         the creator's initials, and a short `-` delimited description, e.g.
    │                         `1.0-jqp-initial-data-exploration`.
    │
    ├── references         <- Data dictionaries, manuals, and all other explanatory materials.
    │
    ├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
    │   └── figures        <- Generated graphics and figures to be used in reporting
    │
    ├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
    │                         generated with `pip freeze > requirements.txt`
    │
    ├── setup.py           <- makes project pip installable (pip install -e .) so src can be imported
    ├── src                <- Source code for use in this project.
    │   ├── __init__.py    <- Makes src a Python module
    │   │
    │   ├── data           <- Scripts to download or generate data
    │   │   └── make_dataset.py
    │   │
    │   ├── features       <- Scripts to turn raw data into features for modeling
    │   │   └── build_features.py
    │   │
    │   ├── models         <- Scripts to train models and then use trained models to make
    │   │   │                 predictions
    │   │   ├── predict_model.py
    │   │   └── train_model.py
    │   │
    │   └── visualization  <- Scripts to create exploratory and results oriented visualizations
    │       └── visualize.py
    │
    └── tox.ini            <- tox file with settings for running tox; see tox.testrun.org


--------

<p><small>Project based on the <a target="_blank" href="https://drivendata.github.io/cookiecutter-data-science/">cookiecutter data science project template</a>. #cookiecutterdatascience</small></p>
