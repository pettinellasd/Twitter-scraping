<h1 align="center">Twitter scraping and sentiment analysis</h1>
<h3 align="center">Scrape, Filter, Analyze</h3>

The cryptocurrency market is dominated by small private investors and large institutional investors represent only a small slice of it; ergo, what is perceived from social media platforms, as well as from the news in the newspapers, can represent a way for identifying the behavior of the average investor. Many times has been demonstrated how social media data can be used to outline investor sentiment:
[for example see: https://royalsocietypublishing.org/doi/10.1098/rsos.150288, or https://journals.plos.org/plosone/articleid=10.1371/journal.pone.0161197]

For the Twitter scraping and sentimental analysis procedure, the main libraries used are the following:

• snscrape: is a scraper for social networking services (SNS). It scrapes elements such as user profiles, hashtags or searches and returns, after setting the constraints, the desired elements (e.g. relevant posts). Its great advantage is the fact that it does not require the use of the API and this nullifies the limit to the number of tweets that can be retrieved or the tweet window (ie the date range of the tweets). Then Snscrape allows you to recover old data.
• Pandas: it is also an open source Python library widely used for data analysis. It is based on another package called Numpy, which provides support for multidimensional arrays. It is arguably the most popular data management tool, in fact it works well with many other data science modules within the Python ecosystem and is usually already included in distributions of Python itself. Through this library the execution of many of the repetitive and time-consuming tasks (cleaning, filling, normalizing, etc… of data) have been simplified and speeded up.

Before introducing the third and last library used, let's define the concept of NLP (Natural Language Processing). 
It consists in a process of manipulating or even understanding text or speech by any software or machine. An analogy is that humans interact and understand each other's opinions and respond with the appropriate response. In NLP, this interaction, understanding and response is done by a computer instead of a human being.

• The Natural Language Toolkit (NLTK) library is a suite that contains libraries and programs for statistical processing of the language. It is one of the most powerful NLP libraries, containing packages for making machines understand human language and respond to it with an appropriate response.
        - The module named “VADER” (Valence Aware Dictionary for Sentiment Reasoning) has been added to the NLTK library. Thanks to this component, provided by a Python3 API, the model is pre-trained. The analysis of sentiment seeks, through the deduction of the choice of words and from the structure of the text, an estimate of the sentiment. VADER will assign a proportional polarity score for positive, neutral, and negative sentiment, as well as providing a single compound score ranging from -1 to 1.
        
        
1) Once the libraries and modules have been imported, you can proceed with the script.
First a list is initialized in which to add, through the for loop, the scraped tweets which, subsequently, will be placed in a csv file.
2) Continue by activating the libraries relating to scraping and sentiment analysis, setting the useful date for the purposes of the research and the "compound" column in the csv file that will reveal the sentiment values assigned.
3) After these two processes it is possible to actually write the csv file in the desired format, that is three columns containing the posts, the sentimental analysis value, and the date and time when the post was scraped.
4) For convenience it has been chosen to write a csv file in the structure as above for each day of the month.
However, to feed all the data to the forecasting model via a single input, it is necessary to combine them in a single file.
5) A final precaution was to make sure that the scraped posts were exclusively in English, to allow a better comparison with the data collected from other channels as well. For this was used the langdetect library, made available by Google for language detection.
6) Finally, exclusively to have a form of graphic summary visualization of the scraping, we proceeded to calculate the average of the sentimental value per hour and to create a trendline that places the “Sentiment Compound” column on the Y and the time value on the X axis.
