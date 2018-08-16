## Requirement
* python 3
* pytorch > 0.1
* torchtext > 0.1
* numpy

## Result
I just tried two dataset, MR and SST.

|Dataset|Class Size|Best Result|Kim's Paper Result|
|---|---|---|---|
|MR|2|72%(CNN-rand-static)|76.1%(CNN-rand-nostatic)|
|SST|5|37%(CNN-rand-static)|45.0%(CNN-rand-nostatic)|


## Train
```
./main.py
```
You will get:

```
Batch[100] - loss: 0.655424  acc: 59.3750%
Evaluation - loss: 0.672396  acc: 57.6923%(615/1066) 
```

The snapshot option means where your model load from. If you don't assign it, the model will start from scratch.

## Predict
* **Example1**

	```
	./main.py -predict="Hello my dear , I love you so much ." \
	          -snapshot="./snapshot/2017-02-11_15-50-53/snapshot_steps1500.pt" 
	```
	You will get:
	
	```
	Loading model from [./snapshot/2017-02-11_15-50-53/snapshot_steps1500.pt]...
	
	[Text]  Hello my dear , I love you so much .
	[Label] positive

## Reference
* [Convolutional Neural Networks for Sentence Classification](https://arxiv.org/abs/1408.5882)

