# JHU-CUT
Code, data, and models from ["Civil Unrest on Twitter (CUT): A Dataset of Tweets to Support Research on Civil Unrest" EMNLP 2020 W-NUT](http://noisy-text.github.io/2020/pdf/2020.d200-1.28.pdf)

## Dataset
The data is in `/data`. As per Twitter guidelines it only contains the tweet IDs and not the full tweet content.

* `keywords_english.txt`: Civil unrest-related keywords
* `known_annotations.csv`: "Cround truth" annotations by the authors used to evaluate Mechanical Turk worker annotations
* `labelled_tweets_is_general_unrest.csv`: Labels for tweets (IDs only) and whether they were annotated as "general unrest" and "specific/nonspecific event"
* `labelled_tweets_is_protest_event.csv`: Labels for tweets (IDs only) and whether they were annotated as "specific/nonspecific event"
* `majority_annotation_results.csv`: All labels for the tweets (IDs along with year and country)

## Civil Unrest Event Prediction Models
We evaluated ngram and embedding-based models on how well they can identify tweets discussing specific/nonspecific protests and riots (`/data/labelled_tweets_is_protest_event.csv`). See the above paper for details.

The below trained models are in `/results`.

**Ngram Models**

The Keyword model and Unigram model had F1 0.782 and 0.775 F1, respectively.

* Code: `ngram_model.py`
* Run settings: `run_ngram_models.sh`

Note: these scripts handle both the general ngram and civil unrest-related keyword count models.

**BERTweet model**

This model was not included in the final paper and is still being improved. Currently achieves an F1 of 0.814.

* Code: `bertweet_model.py`
* Run settings: `run_bertweet_model.sh`

Note: Using a GPU for BERTweet is highly recommended

---

Please email Alexandra DeLucia if you have any issues or questions (aadelucia@jhu.edu). 

