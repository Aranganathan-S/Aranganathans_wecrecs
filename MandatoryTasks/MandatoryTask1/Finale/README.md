# English → French QA Pipeline

Extract answers from English context using a pretrained QA model and translate them to French using a pretrained translation model. Uses Hugging Face models only, no training required. Ready to run in Kaggle or any Python environment.

## Architecture
- Input: English context + question  
- QA Module: `deepset/roberta-base-squad2` → outputs English answer  
- Translation Module: `Helsinki-NLP/opus-mt-en-fr` → outputs French answer  
- Output: English and French answers

## Requirements
- Python 3.8+  
- Libraries: `transformers`, `torch`  
- Install: `pip install transformers torch`

## Usage
```python
from src.qa_translate import english_to_french_qa

context = "Harry Potter is a series written by J.K. Rowling."
question = "Who wrote the Harry Potter series?"

english_answer, french_answer = english_to_french_qa(question, context)
print("English Answer:", english_answer)
print("French Answer:", french_answer)
```



## Evaluation
- **QA:** Exact Match (EM), F1 score  
- **Translation:** BLEU or ChrF for short answers  

## Notes
- QA is extractive; context must contain the answer  
- Names/entities usually remain unchanged in translation  
- Translation model can be swapped for other languages  
- Batch translation improves speed on large datasets  

