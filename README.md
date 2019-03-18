# BERT NER

Use google BERT to do CoNLL-2003 NER !


# Requirements

-  `python3`
- `pip3 install -r requirements.txt`

# Run

`python run_ner.py --data_dir=data/ --bert_model=bert-base-cased --task_name=ner --output_dir=out --max_seq_length=128 --do_eval`


# Result
```
             precision    recall  f1-score   support

       MISC     0.9407    0.9304    0.9355       273
        LOC     0.9765    0.9905    0.9834       419
        PER     0.9814    0.9814    0.9814       322
        ORG     0.9706    0.9792    0.9749       337

avg / total     0.9690    0.9734    0.9711      1351
```

# Inference

```python
from bert import Ner

model = Ner("out/")

output = model.predict("Steve went to Paris")

print(output)
# {
#     "Steve": {
#         "tag": "B-PER",
#         "confidence": 0.999879002571106
#     },
#     "went": {
#         "tag": "O",
#         "confidence": 0.9968552589416504
#     },
#     "to": {
#         "tag": "O",
#         "confidence": 0.9996656179428101
#     },
#     "Paris": {
#         "tag": "B-LOC",
#         "confidence": 0.999504804611206
#     }
# }

```


### Tensorflow version

- https://github.com/kyzhouhzau/BERT-NER