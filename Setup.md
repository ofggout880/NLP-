
# NLP Cleaning the database 

Tring to import and clean my df of consumer's feedback 

## First step import from my drive the test files  

```bash
import pandas as pd
import numpy as np
from google.colab import drive
import re

drive.mount('/content/drive')

file_path = '/content/drive/MyDrive/CODING/Python/feedbacks_SNCF.csv'

df = pd.read_csv(file_path, encoding_errors='ignore', sep=';')

df.head()
```
## Large cleaning 

```bash
df.drop_duplicates(inplace=True)
df.dropna(subset=['verbatim insat'], inplace=True)  # si 'verbatim insat' est la colonne principale

def clean_text(text):
    text = text.lower()
    text = re.sub(r'[^a-zA-ZÀ-ÿ0-9\\s]', '', text)
    text = re.sub(r'\\s+', ' ', text)
    return text.strip()

df['verbatim_insat_clean'] = df['verbatim insat'].apply(clean_text)
if 'emstr' in df.columns:
    df['emstr_clean'] = df['emstr'].apply(clean_text)
```
## SPacy et la Lemmatisation 

### Installation Spacy + Model Fr
```bash
!pip install -U spacy
!python -m spacy download fr_core_news_sm
import spacy
nlp = spacy.load("fr_core_news_sm")
```

### Lemmatisation  
```bash
def preprocess(text):
    doc = nlp(text)
    tokens = [token.lemma_.lower() for token in doc
              if not token.is_stop and not token.is_punct]
    return " ".join(tokens)

df['verbatim_preproc'] = df['verbatim_insat_clean'].apply(preprocess)
```
