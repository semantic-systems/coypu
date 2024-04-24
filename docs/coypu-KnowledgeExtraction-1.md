# Knowledge Extraction module for Coypu project
## Requirement
- python>=3.7.0
- Jave
- stanford_openie(https://github.com/philipperemy/stanford-openie-python)

## Overview
This repository is a simple implementation for relation extraction and entity linking on twitter text. 
The workflow is as folllows:
Tweet ----> extracted triples -----> link entity to wikidata through wikidata api.


### How to run an example?
```
pip install stanford_openie
python ie.py
```
Replace the text by the twitter you want to work on:
extractor.AnnoText('Fire breaks out in Hawaii', save=True) ---> extractor.AnnoText('Your own text', True)

The code will return you the triples from that text in json form.

```json
{
    "subject": "Fire",
    "relation": "breaks out in",
    "object": "Hawaii",
    "sublink":
        {
            "pid": "P910",
            "property": "topic's main category",
            "eid": "Q4992738",
            "entity": "Category:Fires"
        },
    "oblink":
        {
            "pid": "P6",
            "property": "head of government",
            "eid": "Q469689",
            "entity": "Neil Abercrombie"
        }
}
```

This result will be saved to triple.json file under the same directory since we give True to save argument.

## Pipeline
The pipeline of this module is based on following parts:
1. A txt2graph class, which extract the triples in a given text. (Based on openie)
2. A entLink class, which links the found entities using the wikidata entity search API.
