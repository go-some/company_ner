# company_ner



spaCy 

```python
$> pip install -U spacy

# 언어별 모델 설치# 한국어 지원 안함 
python -m spacy download en
python -m spacy downlonad de
python -m spacy download es
python -m spacy downlonad pt
python -m spacy download fr
python -m spacy downlonad it
python -m spacy download nl


```


```python
import spacy
nlp = spacy.load('en')

f = open("article_test.txt", "r")

for d in f:
    doc = nlp(d)
    for ent in doc.ents:
        if ent.label_ == "ORG":
            print(ent.text)
```
---
기사 본문에서 추출된 회사 이름들

The Investors Intelligence Bull/Bear Ratio  
The Cboe Options Exchange Volatility Index VIX  
The Cboe Options Exchange  
Cboe  
Coronavirus  
Conagra Brands CAG  
Keurig Dr Pepper KDP  
Johnson & Johnson JNJ  
Monmouth Real Estate Investment MNR  
Vickers Insider Weekly  
CNBC  
Baird  
ProShares  
ProShares  
Apple AAPL  
Google GOOG  
Amazon.com  
ProShares Short QQQ PSQ  
Direxion Daily Technology  
+7.07%  
ProShares UltraPro Short QQQ SQQQ  
Direxion Daily Semiconductor  
Shares SOXS  
ProShares UltraShort Semiconductors SSG  
Baird  
CAG  
KDP  
JNJ  
ADC  
MNR  
GOOGL  
  
숫자로 나오는 경우는 제외해야할 것 같음.  
