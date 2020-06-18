# Evaluation Datasets for Contextual Text Classification

This repo contains the evaluation datasets used in the following manuscript:

Yiping Jin, Dittaya Wanvarie, Phu T. V. Le, Learning from Noisy Out-of-Domain Corpus Using Dataless Classification. Natural Language Engineering (2020). DOI: [https://doi.org/10.1017/S1351324920000340](https://doi.org/10.1017/S1351324920000340) 

There are two evaluation datasets: 

- *browsing-dataset*: contains a list of 1,501 manually annotated documents. Each document can be assigned one or more labels.
- *news-crawl-v2-dataset*: contains a list of 2,127 documents whose labels are mapped from the news categories. In this corpus, each document is assigned only one label.

Both datasets contains the following list of 22 categories:

```
IAB1 	 arts-entertainment
IAB2 	 automotive
IAB3 	 business
IAB4 	 careers
IAB5 	 education
IAB6 	 family-parenting
IAB7 	 health-fitness
IAB8 	 food-drink
IAB9 	 hobbies-interests
IAB10 	 home-garden
IAB11 	 law-gov-t-politics
IAB12 	 news
IAB13 	 personal-finance
IAB14 	 society
IAB15 	 science
IAB16 	 pets
IAB17 	 sports
IAB18 	 style-fashion
IAB19 	 technology-computing
IAB20 	 travel
IAB21 	 real-estate
IAB22 	 shopping
IAB23 	 religion-spirituality
```

## Corpus Data Format

### browsing-dataset

It contains two folders, `document/` and `label/`. There's a one-to-one correspondance between the label file and the document file. I.e. the file `label/0.txt` is the label(s) for the document `document/0.txt`. The labels are the IAB label code (IAB\*\*). In case a document has more than one label, they're comma deliminated.

### news-crawl-v2-dataset

The corpus contains documents organized in one folder per category. E.g. the folder `automotive/` contains all documents belonging to automotive category.

## Input Data Format

The prediction of the model should be stored in the following csv format:

```
1053.txt,home-garden
1735.txt,careers
289.txt,style-fashion
2214.txt,food-drink
```

Where each line contains the document file name and the predicted label.

The script `browsing-dataset/evaluate.py` was used to produce the stats we presented in the manuscript.
