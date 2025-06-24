### **Manual TF-IDF vs. CountVectorizer vs. TfidfVectorizer**

We implemented TF-IDF manually and compared results with `CountVectorizer` and `TfidfVectorizer` from scikit-learn using the corpus:

```python
corpus = [
    'the sun is a star',
    'the moon is a satellite',
    'the sun and moon are celestial bodies'
]
```

In CountVectorizer,

- Purely counts word occurrences
- No consideration of word importance across documents
- Common words like "the" will get high counts

But in TfidfVectorizer (Scikit-learn) & Manual TF-IDF,

- Combines **Term Frequency (TF)** and **Inverse Document Frequency (IDF)**
- Common words (appearing in many documents) have lower IDF, reducing their TF-IDF
- Rare words (unique or infrequent) get higher TF-IDF

CountVectorizer treats all words equally, so only raw counts matter. TF-IDF penalizes frequent, generic words like "the", "is", "and".
