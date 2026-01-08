Semantic and Sentiment Analysis of Song Lyrics (1970-2020)
========================================================

This project analyzes how themes and sentiment in English pop and rap song lyrics
have evolved from 1970 to 2020 using Natural Language Processing (NLP) methods.
The analysis combines topic modeling (NMF) with lexicon based sentiment analysis
(VADER) to study cultural and emotional trends in popular music over time.

The repository accompanies an academic research paper and provides a reproducible
analysis pipeline.

------------------------------------------------------------
Goals
------------------------------------------------------------

1) Identify dominant lexical-semantic themes in pop and rap lyrics
2) Track how these themes change over time
3) Analyze how lyrical themes are associated with sentiment
4) Relate observed patterns to broader social and cultural change

------------------------------------------------------------
Dataset
------------------------------------------------------------

Source:
- Genius Song Lyrics dataset (Kaggle)

Scope:
- Genres: Pop and rap
- Language: English only
- Years: 1970-2020

Sampling:
- Top 100 most-viewed songs per genre per year on Genius
- Exposure-based sampling to approximate mainstream consumption

Final size:
- Approximately 9400 songs

Note:
Lyrics may contain explicit or offensive language. Terms are preserved for
analytical accuracy and do not reflect the author's views.

------------------------------------------------------------
Methodology
------------------------------------------------------------

1) Text Preprocessing
   - Removal of stage directions, URLs, and metadata
   - Unicode normalization and lemmatization
   - Stopword removal (negators preserved)
   - Domain-specific filtering of fillers and ad-libs

2) Feature Engineering
   - TF-IDF unigram representation
   - Vocabulary pruning using document frequency thresholds

3) Topic Modeling
   - Model: Non-Negative Matrix Factorization (NMF)
   - Number of topics: 7
   - Output:
     * Document-topic matrix (topic proportions per song)
     * Topic-term matrix (top words per topic)

4) Sentiment Analysis
   - Tool: VADER
   - Sentiment classes: positive, negative, neutral, ambiguous
   - Analysis performed at song level and topic-weighted yearly level

5) Statistical Analysis
   - Correlations between topic prevalence and sentiment
   - OLS regressions on yearly trends
   - Residual diagnostics

------------------------------------------------------------
Key findings
------------------------------------------------------------

- Explicit and violent language increases sharply after the early 1990s
- Party/disco vocabulary peaks in the late 1970s and declines afterward
- Most lyrical themes become more negative over time, even when topics remain stable
- Violence/profanity is strongly associated with negative sentiment
- Romance, imagery, and religion correlate positively with positive sentiment

These trends align with:
- The mainstream rise of hip-hop
- Secularization
- Normalization of explicit language
- A long-term emotional “darkening” of popular lyrics

------------------------------------------------------------
Requirements
------------------------------------------------------------

Python 3.x

Key libraries:
- pandas
- numpy
- scikit-learn
- nltk
- matplotlib
- vaderSentiment

------------------------------------------------------------
Usage
------------------------------------------------------------

1) Open NLP_lyrics.ipynb
2) Run cells in order to:
   - Load and preprocess data
   - Train TF-IDF and NMF models
   - Compute sentiment scores
   - Generate plots and tables
3) Refer to NLP_paper.pdf for full theoretical context and interpretation

------------------------------------------------------------
Limitations
------------------------------------------------------------

- Lexicon-based sentiment models may misinterpret slang, irony, or dialect
- Results emphasize trends and direction rather than absolute sentiment levels
- Analysis focuses on mainstream English-language music only

------------------------------------------------------------
Future work
------------------------------------------------------------

- Dialect-aware or transformer-based sentiment models
- Genre-conditional topic modeling
- Multilingual lyric analysis
- Integration of audio features with lyrical analysis

