---
layout: default
title: Lord of The Rings - Project 
---

# Analyzing Lord of The Rings with Data Science

## Overview 

1. [Introduction](#1---introduction)
2. [Data](#2---data)
3. Networks
4. Basic Analysis
5. Community Detection
6. Text analysis
7. Sentiment analysis

## 1 - Introduction 

{% include video.html %}

## 2 - Data
We divided our analysis in three different ones, based on the datasets we had.

#### 1. The fan Wiki of Lord of The Rings

[Here's the link to the wiki](http://lotr.wikia.com/wiki/Main_Page) where we extracteed the content of all the wikipages from all the characters present in Lord Of the Rings story.

If you want to download the files containing the wikipages data [click here](https://github.com/Nab-88/social-graphs-and-interactions/blob/master/datasets/characters.zip). (You will have access to a .zip files containing a .txt file for each characters of the wiki.)


#### 2. Transcripts of the movie

We found a dataset, containing what the characters of the movies are saying. [Click here to have access to our trasncripts.](https://github.com/Nab-88/social-graphs-and-interactions/blob/master/datasets/lotr_scripts.csv)

#### 3. Books

We downloaded the three books from J.R.R Tolkien from [this website.](https://archive.org/)
Here you can download the books we used for our project.
- [Book 1 - The Fellowship of the Rings](https://github.com/Nab-88/social-graphs-and-interactions/blob/master/datasets/LOTR1_book_CLEAN.txt)
- [Book 2 - The Two Towers](https://github.com/Nab-88/social-graphs-and-interactions/blob/master/datasets/LOTR3_book_CLEAN.txt)
- [Book 3 - The Return of the King](https://github.com/Nab-88/social-graphs-and-interactions/blob/master/datasets/LOTR2_book_CLEAN.txt)


#### Click here to dowload our datasets.

## 3 - Networks

#### 1. Network based on the link inside the wikipages

Nodes are the characters and edges are the link from the wikipage of one character to another one.

#### 2. Network based on the chapters of the books

Nodes are the characters and there is an edge between two characters each time there appear in the same chapter

## 4 - Basic Analysis 

To do for both of the networks

#### Who is the most connected charaters 

Here we have to :
- precise if there are differences between the graph and to interpret these differences
- Analyse the result 
- Find funny or weird result

#### Degree distribution

Here we have to:
- Analyse the results
- Explain a intersting fact to explain to the readers

## 5 - Community detection

Here we have to:
- Create community for the most relevant graph
- Analyse them and explain the results
- Create community based on race or culture
- Compare them
- And find the ties between community with cconfusion matrix


## 6 - Sentiment analysis

### 6.1 - Sentiment analysis over characters


We also wanted to know who are the nicest and badest guys in each book.

We performed a sentiment analysis over each book:

![alt text](./assets/LOTR1_sent_movie.png "Ranking for movie 1")

![alt text](./assets/LOTR2_sent_movie.png "Ranking for movie 2")

![alt text](./assets/LOTR3_sent_movie.png "Ranking for movie 3")

| Book                          | Top 3 Nicest        |Top 3 Baddest |
| -----------------------------:|--------------------:| -------:|
| The Fellowship of the Ring    | Bilbo, Pippin, Barliman        | Sam, Boromir, Saruman    |
| The Two Towers                | Boromir, Arwen, Soldier          | Grima, Smeagol, Orc    |
| The Return of The King        | Treebeard, Bilbo, Smeagol          | Gothmog, Eomer, Legolas    |

---

To summarize all the sentiments of the characters here is the ranking of the characters from the Nicest (on the left) to the baddest (on the right)

![alt text](./assets/lotr_sent_total.png "Ranking for characters who appears in the three movies")


More generally, it appears that Bilbo is one of the nicest person in the Middle Earth and especially all the hobits like Merry and Pippin and nice persons. But this analysis confirms what we were expecting, that Orcs, Gothmog and Grima are really bad persons. 
But we also have some suprise like Saruman who is in th middle of the ranking which could be explain because in the beginning of the story is lying to Gandalf and faking to be a good magician.


![alt text](./assets/bilbo_wc.png "Most frequent words for Bilbo")


![alt text](./assets/saruman_wc.png "Most frequent words for Saruman")

We can see that the most words most frequently said by Saruman are : Burn, Sauron, Fire, War ...

### 6.2 - Evolution of sentiments over the books

Thanks to the sentiment analysis we performed we are able to know when are the darkest and the happiest time of the story

![alt text](./assets/sentiment.png "Evolution of sentiments through the story chapter by chapter")

We then try to know  what happens during these two moments: chapter X and chapter Y.
Then we performed a text analysis on those two chapters, here are the words clouds of these two chapters:

-->include word cloud when gandalf dies <--

-->include word cloud when merry and pippin are back <--


### 6.3 - When a specific words is appearing in the story

  Plot this.
