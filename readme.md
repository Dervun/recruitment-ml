# 0. code location

All the code and outputs are in the _prototyping.ipynb_ file.


# 1. pipenv

I use pipenv for virtual environment management.

You need python 3.6+ (ideally 3.9, as specified the *"Pipfile"*) and **pipenv** installed via **pip** (or **pip3**) in there.

## Main artifacts

* *Pipfile* -- consists of the list of installed libraries, sometimes with specifications like "pandas>=1.0", but it's flexible;
* *Pipfile.lock* -- consists of the data of the exact working environment, exact library versions, all the dependencies.

## Installation and updating

You can install this environment with the following commands:

Install from *"Pipfile"* (for the latest versions):  
`pipenv install`

Install from *"Pipfile.lock"* (for the exact versions specified in Pipfile.lock):  
`pipenv sync`

To install any new libraries, just use `pipenv install ...` instead of the usual `pip install ...`

## Activation

You can activate the environment in your shell:  
`pipenv shell`

Or start each command with `pipenv run`, for example:

```bash
pipenv shell
python script1.py
python script2.py
```

or

```bash
pipenv run python script1.py
pipenv run python script2.py
```


So, **summing up**, to open, edit and run _jupyter notebooks_, you can do the following:
```bash
python3.9 -m pip install pipenv
python3.9 -m pipenv shell
jupyter-lab
```


# 2. Summary

I decided to make a baseline model (TF-IDF + SVM) and see how it works.
This model demonstrated 0.941±0.006 F1 score on 5-fold validation and 0.944 F1 score on the test (20%) data.


# 3. Good points

* Surprisingly high F1 score for such a simple model.
* This model is pretty simple and fast, and simultaneously has a high accuracy.
* There was made quite a simple data cleansing and that was enough.


# 4. Points for improvements

* I think that class balance in this task is highly optimistic and unlikely in the real data.
  So, I would stick to F1 score and others that work well with the class imbalance.
* Also, I suspect that there are specific sophisticated NN-based models for this type of task (person style recognition).
* To test and deploy it somewhere, I would add unit tests, specific mock tests, specific serving and API and so on depending on the need.
* If necessary, switch to probability-producing model, to balance precision-recall tradeoff.
