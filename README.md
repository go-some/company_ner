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
Coronavirus <--우한폐렴도 회사로 잡아줌  
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

spaCy로 기업명 추출하는 경우, 보정이 필요한데, 기업명 리스트가 필요하여 찾는중
NYSE나 나스닥 공시에서 기업명 리스트를 다운로드 받을수 있게 되어있지 않음.

2017년 9월 기업리스트는 찾음.

---

## stock_list folder
NYSE와 NASDAQ에 상장된 회사 리스트
stock ticker와 full name


NASDAQ : 3578개
NYSE   : 3099

---
## MongoDB atlas 뉴스데이터 time 파싱 필요

<img width="512" alt="스크린샷 2020-02-02 오전 10 56 51" src="https://user-images.githubusercontent.com/10937193/73601796-245cb100-45ab-11ea-8831-0120c1951039.png">

