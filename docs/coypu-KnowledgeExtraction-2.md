# Knowledge Extraction module for Coypu project MVP2
## Requirement
- python>=3.7.0
- pip install -r requirements.txt


Place the model files in the corresponding directory
- download the model from [drive](https://drive.google.com/drive/folders/1CIkN6opztlhgrkiIOOifocaWtY-PQquL?usp=sharing) you want to use under /mvp2/src/ 

## Overview
This repository is a pytorch implementation for relation extraction on twitter text. 
The workflow is as folllows:
Tweet ----> extracted triples

### How to predict an example?
Replace the text by the twitter you want to work on and the model checkpoint you want to use in predict.py:
```
result = token_classifier("Covid breaks out in Hamburg city of Germany in 2022. ^^")
model_checkpoint = 'bert-base-uncased-lsoie/checkpoint-64110'
```
```
python predict.py
```

The code will return you the triples in list form.
```python
[['Covid', 'breaks', 'in Hamburg city of Germany'], ['Covid', 'breaks', 'in 2022']]
```

### How to train?
Change the variable in In config.py
```
dataset="lsoie"/'wnut17'
model_checkpoint=model from huggingface hub/local direcrtory

python train.py
```
## Pipeline
The pipeline of this module is based on following parts:
1. Create dataset from lcoal file/cloud
2. Train the model using trainer api
3. predict using pipeline
