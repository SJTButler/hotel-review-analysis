This project attempts to develop methodologies to quantify the sentiment of Hotel reviews in a large dataset. it contains methods for cleaning the data, (optionally) translating non-english reviews in the dataset, and then four methods for calculating the sentiment of the text:
  - Google Cloud Natural Language API Sentiment Scores
  - SentiWordNet average sentiment scores
  - Naive Bayes Classifier Sentiment Scores (trained using the review ratings)
  - Long Short-Term Memory Neural Network Classifier Sentiment Scores (trained using the review ratings)
  
It also contains evaulations of the pros and cons of each approach, as well as the effectiveness of the specific implementations.

## How to run

To run this project navigate to the folder you wish to download this project to in the command prompt and run

> git clone <https://github.com/SJTButler/hotel-review-analysis.git>

The datasets used can be downloaded at <https://www.kaggle.com/datafiniti/hotel-reviews>. There will be three csv files available - these files should be placed unchanged into a /dataset folder

The notebook can then be opened by running

>jupyter notebook

and opening "Hotel Reviews Sentiment Analysis.ipynb".

NOTE: Some aspects of the project require a Google Service account - to use this in the dataset, change the %env GOOGLE_APPLICATION_CREDENTIALS line in the *Imports and Constants* section of the notebook to point to the credential file for your account. (These parts of the code WILL cost money to run, so be warned)


Alternatively, a html version of the notebook is available to read at <http://hotelreviewanalysis.sjtbutler.co.uk/>

## Libraries used 

- Numpy
- Pandas
- Sci-Kit Learn
- Keras
- TQDM
- Keras-TQDM
- NLTK
- unidecode

- BFG (to deal with accidentally commiting the large datasets to the repo)

## Future Work

While I am very proud of the work I've done on this project, I can see a number of elements that, given more time, I would work to improve, such as:

- Fine tuning the LSTM Model
  - I feel more work could be done to improve the accuracy of the LSTM network, by changing the structure of the network and by further fine-tuning the hyper-parameters (possibly by using automated paramter tuning methods such as sci-kit learn's GridSearchCV or RandomizedSearchCV objects

-Further analysis of the effectiveness of each approach

- Code re-factoring
  -At present, parts of the code - particularly parts dealing with visualisation and computing the difference between the obtained sentiment scores and the given ratings - are copy-pasted with minor changes from other parts of the project, and probably should be condensed into re-usable functions to make the project more maintainable (although, being as it is in a notebook format, I do appreciate the immediacy of having the code right next to the output)
