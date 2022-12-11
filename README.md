# Forward Forward Netowork
#### Quick Start

__Requirement:__ Numpy, pytorch (for the baseline model)

__Benchmark:__ We provide a simple testing pipeline on Iris dataset here. You can run ``python run.py`` and see the results:

```shell
> python run.py

Model: ForwardForwardNetwork
----------------------------------------
Epoch-0 | Spent=0.0000 | Train Accuracy=0.8857
Epoch-100 | Spent=1.4860 | Train Accuracy=0.8857
Epoch-200 | Spent=1.7808 | Train Accuracy=0.9000
Epoch-300 | Spent=1.8341 | Train Accuracy=0.9286
Epoch-400 | Spent=2.2316 | Train Accuracy=0.9429
Epoch-500 | Spent=2.0988 | Train Accuracy=0.9429
Epoch-600 | Spent=1.6456 | Train Accuracy=0.9571
Epoch-700 | Spent=1.4854 | Train Accuracy=0.9429
Epoch-800 | Spent=2.1213 | Train Accuracy=0.9571
Epoch-900 | Spent=1.8460 | Train Accuracy=0.9571
Train Accuracy=0.9429 | F1=0.9487 | AUC=0.9394
Test Accuracy=0.9333 | F1=0.9286 | AUC=0.9412

Model: MLP
----------------------------------------
Train Accuracy=0.9857 | F1=0.9867 | AUC=0.9975
Test Accuracy=0.9000 | F1=0.8696 | AUC=0.9864
```

__Reuse:__ You can simply use it in your project as following:

```python
from forwardforward import ForwardForwardClassifier
model = ForwardForwardClassifier(in_dim, hide_dim, out_dim)
model.fit(trainX, trainY)
predY = model.predict(testX)
evaluate(testY, predY)
```

__Setting: __ BatchSize=32, LearnRate=0.001, epochs=1000，constant theta=0.0.

__Note:__ I found that the model is very sensitive to different hyper-parameters (learn_rate, batch_size, hide_dim). 

__Warning:__ The code right now is based on my PERSONAL understanding to the paper, so it may have some mistake!!!!!

#### References

Paper: Hinton, Geoffrey. "[The Forward-Forward Algorithm: Some Preliminary Investigations]([FFA13.pdf (toronto.edu)](https://www.cs.toronto.edu/~hinton/FFA13.pdf))."

Related Repo: [forward-forward/forward-forward.ipynb at main · Trel725/forward-forward (github.com)](https://github.com/Trel725/forward-forward/blob/main/forward-forward.ipynb).
