# __Commands and Import Packages__

## __commands for your terminal__

### __Pandas__

````

pip install pandas

pip3 install pandas

python -m pip install pandas

````

---

### __Error Messages in SVC or JP__

If the module pd and others was not found , try this, close SVC or JP before and after installation process is completed re-open SVC or JP.

````

! pip3 install pandas

pip install matplotlib

python -m pip install seaborn

pip install --upgrade pip pip install jupyter

pip install scikit-learn

````

---

### __virtual environment__

--> if your Kernel is not selectable in VSC you should c&p this in your Terminal 

````

pyenv local 3.9.4

python -m venv .venv

source .venv/bin/activate

pip install --upgrade pip

pip install -r requirements.txt

````

if Plotly should be used:

````

brew update

brew install node


pip install jupyterlab "ipywidgets>=7.5"

jupyter labextension install jupyterlab-plotly@4.14.3

jupyter labextension install @jupyter-widgets/jupyterlab-manager plotlywidget@4.14.3

````

---

## __commands for your VSC or JN__

````

Import libraries and plots in .ipynb

import pandas as pd

import numpy as np

import matplotlib.pyplot as plt

import seaborn as sns

import plotly.express as px

%matplotlib in line

````
<br />

````

from scipy import stats

import statsmodels.api as sms

Import libraries for modelling and metrics in .ipynb

from sklearn.datasets import make_classification

from sklearn.linear_model import LogisticRegression

from sklearn.model_selection import train_test_split


from sklearn.metrics import mean_squared_error, r2_score

from sklearn.metrics import mean_absolute_error

from sklearn.metrics import confusion_matrix

from sklearn.metrics import accuracy_score

from sklearn.metrics import recall_score

from sklearn.metrics import precision_score

from sklearn.metrics import f1_score

from sklearn.metrics import roc_curve

from sklearn.metrics import roc_auc_score

from sklearn.metrics import classification_report

