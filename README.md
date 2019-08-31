# python_building_blocks
## Python code snippets that do small nifty things 

### 1. Spacy named entity recognition filter:
Returns all text that hasn't been recognised as an named entity.

```python
import spacy
nlp = spacy.load("en_core_web_sm")
doc = nlp(u"Apple is looking at buying U.K. startup for $1 billion")

clean = str(doc)
for ent in doc.ents:
    clean = clean.replace(ent.text, "|")
    
non_entities = list(filter(None,  clean.split("|")))
print (non_entities)
```

[More examples and resources:](https://spacy.io/usage/linguistic-features#named-entities)
