# spaCy

## Using spaCy to Organize and Summarize Textbook Content

### Named Entity Recognition (NER)

1. Load the textbook content into a spaCy `Doc` object:
    ```python
    import spacy

    nlp = spacy.load("en_core_web_sm")
    textbook_content = "Your textbook content here."
    doc = nlp(textbook_content)
    ```

2. Extract named entities using the `ents` attribute of the `Doc` object:
    ```python
    named_entities = [(ent.text, ent.label_) for ent in doc.ents]
    ```

3. Filter entities based on their labels to focus on key concepts:
    ```python
    key_concepts = [ent for ent in named_entities if ent[1] in ["PERSON", "ORG", "GPE", "DATE"]]
    ```

### Part-of-Speech (POS) Tagging

1. Load the textbook content into a spaCy `Doc` object:
    ```python
    import spacy

    nlp = spacy.load("en_core_web_sm")
    textbook_content = "Your textbook content here."
    doc = nlp(textbook_content)
    ```

2. Extract key concepts based on POS tags using the `pos_` attribute of the tokens in the `Doc` object:
    ```python
    key_concepts = [token.text for token in doc if token.pos_ in ["NOUN", "PROPN"]]
    ```

### Dependency Parsing

1. Load the textbook content into a spaCy `Doc` object:
    ```python
    import spacy

    nlp = spacy.load("en_core_web_sm")
    textbook_content = "Your textbook content here."
    doc = nlp(textbook_content)
    ```

2. Extract key concepts based on syntactic roles using the `dep_` attribute of the tokens in the `Doc` object:
    ```python
    key_concepts = [token.text for token in doc if token.dep_ in ["nsubj", "dobj"]]
    ```
