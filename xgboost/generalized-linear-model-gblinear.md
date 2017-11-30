XGBoost has a generalized linear model
======================================

XGBoost is famous for its Boosting Tree Algorithm, but as it turns out XGBoost also implements a
[generalized linear model][kaggle]. This can come in handy if you have a problem that is well
suited for this kind of algorithm.

For a somewhat arbitrary example lets try to fit a model to predict values of the function `y=x*2`.
Our training data in libsvm format could look like the following.

```
0 0:0
2 0:1
4 0:2
6 0:3
8 0:4
```

Lets also write a configuration file for XGBoost so we can use the command-line tool `xgboost` to
train our model.

```
booster = gblinear
objective = reg:linear

data = data.train
test:data = data.train
eval_train = 1
```

With the following command line we can then build our model. The first parameter is the filename
of our configuration file and the optional second parameter reduces the output we see on stdout.

```sh
xgboost xgb.conf silent=1
```

[kaggle]: https://www.kaggle.com/general/25924#post148061
