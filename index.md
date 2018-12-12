---
layout: default
title: Lord of The Rings - Project 
---

# Analyzing Lord of The Rings with Data Science

## Overview 

1. [Introduction](#1---introduction)
2. [Data](#2---data)
3. [Networks](#3---networks)
4. [Basic Analysis](#4---basic-analysis)
5. [Community Detection](#5---community-detection)
6. [Text analysis and Sentiment analysis](#6---sentiment-analysis-and-text-analysis)
7. [More details](#7---more-details)

## 1 - Introduction 

{% include video.html %}

Middle-earth is a world which has cought the imagination of most children growing up in this current and last century, and certainly all of our group members,a world created by J.R.R. Tolkien. The most notable recent appearences of this amazing story and the one which we are going to analyze in this assignment its portrayed in the recent film trilogy directer by Peter Jackson. We also will be examinining the fan created One Wiki to Rule Them All, and the three novels originally published in 1954 and 1955.

Due to our focus only being on the Lord of the Rings, and not on other work by J.R.R. Tolkien, we only downloaded the data of characters present in the trilogy. the number of mentioned characters of Middle-earth on the website is 988, but only 152 of them are present in Lord of the Rings trilogy movies. We also found the novels and movie transcripts on archive.org.

The final goal of this experiment is to understand the movies (the trilogy) and books better in order to see the differences between them. To see how the character related to each other, see the importance of the characters from both the movies and the book. We also wnat to understand the sentiment of each book and character and see the evolution of the sentiment throughout.

## 2 - Data
We divided our analysis in three different sections, based on the datasets obtained.

#### 1. The fan Wiki of Lord of The Rings

[Here's the link to the wiki](http://lotr.wikia.com/wiki/Main_Page) where we extracted the content of all the wikipages from all the characters present in Lord of the Rings story.

If you want to download the files containing the wikipages data [click here](https://github.com/Nab-88/social-graphs-and-interactions/blob/master/datasets/characters.zip). (You will have access to a .zip files containing a .txt file for each characters of the wiki.)


#### 2. Transcripts of the movie

We found a dataset, containing what the characters of the movies are saying. [Click here to have access to our transcripts.](https://github.com/Nab-88/social-graphs-and-interactions/blob/master/datasets/lotr_scripts.csv)

#### 3. Books

We downloaded the three books by J.R.R Tolkien from [this website.](https://archive.org/)
Here you can download the books we used for our project.
- [Book 1 - The Fellowship of the Ring](https://github.com/Nab-88/social-graphs-and-interactions/blob/master/datasets/LOTR1_book_CLEAN.txt)
- [Book 2 - The Two Towers](https://github.com/Nab-88/social-graphs-and-interactions/blob/master/datasets/LOTR3_book_CLEAN.txt)
- [Book 3 - The Return of the King](https://github.com/Nab-88/social-graphs-and-interactions/blob/master/datasets/LOTR2_book_CLEAN.txt)


## 3 - Networks

We chose to print only the network based on the chapters of the books. If interested, the other network can be seen in the notebook. See the link in [part 7](#7---more-details).

#### 1. Network based on the link inside the wikipages

Nodes are the characters and edges are the link from the wikipage of one character to another one.

This network was created as a directed graph. It has 153 nodes and 843 edges with an average in- and out-degree of 5.509


#### 2. Network based on the chapters of the books

We have created a network based on the books. Therefore, we look at each chapter and analyzed who were the characters in this chapter. If two characters are in the same chapter it means that they are connected, so there is a link between them.
That's how we build the network that you can see below:

This graph was created as an undirected graph. It has 125 nodes and 1105 edges with an average degree of 17.68.

![alt text](./assets/All_books_graph.png "Network based on the chapters of the books")

> The friendship paradox is the phenomenon that most people have fewer friends than their friends have, on average.

The network based on the link inside wikipages passes the friendship paradox easily. However the network based on the chapters in the book does not in every instance, meaning that the networks there do actually not follow the power law.This also means that there are many large nodes in the graph and few smaller.


## 4 - Basic Analysis 


> In this section we decided to present the basic analysis we did on the Network obtained with the Wikipages.


| Degree | Eigenvector | Betweeness |
| ----------------:| -------:|-------:|
|Frodo (0.55)   | Sauron (0.33)       |Frodo (0.12)   | 
|Gandalf (0.44)  | Gandalf (0.311)       |Gandalf (0.089)	   |
|Saruman (0.37)   | Frodo (0.310)     |Eowyn (0.084)   | 
|Sauron (0.32)   | Elrond (0.27)      |Merry (0.066)   | 
|Merry (0.31)   | Gimli (0.26)    |Saruman (0.065)   |
|Pippin (0.30)   |  Legolas (0.249)       |Háma (0.063)   |
|Legolas (0.27)  | Galadriel (0.246)     | Sam (0.06)       |
|Galadriel (0.26)   | Saruman (0.23)       |Gamling (0.058)   | 
|Sam (0.26)   | Gollum (0.18	)     |Grishnákh (0.051)    |
|Gimli (0.25)   | Sam (0.17)       |Théoden (0.051)| 




#### Degree:

> The degree centrality measures how a character is connected in the network.

So as we could expect Frodo is the most connected character (a degree of 0.54 means that Frodo is connected to 54% of the characters of the story).

Surprisingly Merry and Pippin are the 3rd and 4th most connected characters, this could be explain by the fact that during the story they have been seperated from the other members of the Fellowship of the Rings, and during this time alone, they met a lot of secondary characters.

#### Eigenvector:

> The eigenvector centrality measures the influence of a character in the network.

Unsurprisingly, Sauron is the most influent character of the story. Which can be explain because he is the person who created the Rings, so he's basically the Lord of the Rings.

Gollum also appears in the top 10 most influent characters of the story because he plays a key role in the story when he helps Frodo to bring the Ring to Mordor.

One thing worth noticing, is that there is a good number of "wise" characters (Gandalf, Elrond, Galadriel, Saruman (even if he is bad)) in the top 10, this is because they have a lot of influence over other characters throughout the story.

#### Betweeness:

> The betweeness centrality measures how central is a character in the network. A character with high betweeness centrality would have more control over the network because a lot of information will pass through him.

Here Éowyn and Háma are very high in the ranking even if they are secondary characters, because they are the link between important characters and other character. For example Hàma is the right-hand of Théoden, so he has importance if you want to reach Théoden.

#### Lord of the Rings Awards

We wanted to present the most important characters of the Lord of the Rings through the centrality scores of the network created by the wikipages. We created a competition between the characters, and gave them a score between 1 and 10 based on their placement in the centrality ranking.

Here's the podium:

![alt text](./assets/final_podium.png "Top 3 most important characters in Lord of the Rings")

- Frodo = 28 points
- Gandalf = 27 points
- Saruman and Sauron = 17 points each

So we can see that Frodo is the most connected character, with Gandalf having almost the same score than him. Saruman and Sauron seem to be equally connected. So, Frodo is the real Lord of the Rings.


## 5 - Community detection

In order to detect communities in the network we implemented the Louvain algorithm. An efficient, simple and easy-to-implement method for identifying communities in large networks.

| Community   1        | Community 2              | Community 3          | Community 4                 | Community 5             | Community 6               | Community 7              | Community 8 | Community 9                    | Community 10 | Community 11 |
|----------------------|--------------------------|----------------------|----------------------------|-------------------------|---------------------------|--------------------------|-------------|--------------------------------|--------------|--------------|
| Galdor of the Havens | Grishnákh                | Galadriel            | Hirluin                    | Rúmil (Noldo)           | Milo Burrows              | Fastred (Pelennor Fields | Herefara    | Théoden                        | Targon       | Beechbone    |
| Nob                  | Arod                     | Thranduil            | Bergil                     | Ufthak                  | Old Noakes                |                          |             | Wídfara                        |              |              |
| Peregrin Took        | Bill Ferny               | Gimli                | Forlong                    | Lagduf                  | Mrs. Proudfoot            |                          |             | Théodred                       |              |              |
| Farmer Maggot        | Gárulf                   | Dáin II Ironfoot     | Boromir                    | Samwise Gamgee          | Widow Rumble              |                          |             | Dúnhere                        |              |              |
| Frodo Baggins        | Saruman                  | Elladan and Elrohir  | Gandalf                    | Landroval               | Lotho Sackville-Baggins   |                          |             | Elfhelm                        |              |              |
| Old Man Willow       | Snaga (Grishnákh's band) | Mouth of Sauron      | Duilin                     | Meneldor                | Melilot Brandybuck        |                          |             | Éowyn                          |              |              |
| Bob                  | Willie Banks             | Haldir (Lorien)      | Ingold                     | Anborn                  | Lindir                    |                          |             | Herubrand                      |              |              |
| Treebeard            | Mat Heathertoes          | Grimbeorn            | Golasgil                   | Wilcombe (Jolly) Cotton | Will Whitfoot             |                          |             | Gothmog (Lieutenant of Morgul) |              |              |
| Rorimac Brandybuck   | Hasufel                  | Sauron               | Denethor II                | Rúmil of Lórien         | Daddy Twofoot             |                          |             | Erkenbrand                     |              |              |
| Fredegar Bolger      | Mauhúr                   | Éothain              | Beregond (Captain)         | Snaga                   | Sancho Proudfoot          |                          |             | Ceorl                          |              |              |
| Tom Bombadil         | Éomer                    | Glóin                | Baranor (Gondor)           | Carl Cotton             | Otho Sackville-Baggins    |                          |             | Witch-king's Fellbeast         |              |              |
| Bregalad             | Finglas                  | Glorfindel           | Dervorin                   | Mablung the Ranger      | Bilbo Baggins             |                          |             | Gléowine                       |              |              |
| Meriadoc Brandybuck  | Uglúk                    | Erestor              | Imrahil                    | Tolman Cotton           | Everard Took              |                          |             | Gamling                        |              |              |
| Fimbrethil           | Lugdush                  | Durin's Bane         | Ioreth                     | Robin Smallburrow       | Bruno Bracegirdle         |                          |             | Witch-king of Angmar           |              |              |
| Goldberry            | Hob Hayward              | Círdan               | Angbor                     | Orophin                 | Lobelia Sackville-Baggins |                          |             | Harding                        |              |              |
| Ted Sandyman         |                          | Elrond               | Faramir                    | Damrod                  | Dora Baggins              |                          |             | Ghân-buri-Ghân                 |              |              |
| Barliman Butterbur   |                          | Beorn                | Derufin                    | Gorbag                  | Odo Proudfoot             |                          |             | Grimbold                       |              |              |
| Watcher in the Water |                          | Asfaloth             | Hurin (Warden of the Keys) | Bowman Cotton           | Hamfast Gamgee            |                          |             | Déorwine                       |              |              |
| Folco Boffin         |                          | Arwen                | Duinhir                    | Gwaihir                 | Angelica Baggins          |                          |             | Windfola                       |              |              |
|                      |                          | Aragorn II Elessar   |                            | Déagol                  | Adelard Took              |                          |             | Háma                           |              |              |
|                      |                          | Halbarad             |                            | Shagrat                 | Hugo Bracegirdle          |                          |             | Gríma Wormtongue               |              |              |
|                      |                          | Celeborn             |                            | Rosie Cotton            |                           |                          |             |                                |              |              |
|                      |                          | Firefoot             |                            | Radbug                  |                           |                          |             |                                |              |              |
|                      |                          | Legolas              |                            | Gollum                  |                           |                          |             |                                |              |              |
|                      |                          | Gildor Inglorion     |                            | Muzgash                 |                           |                          |             |                                |              |              |
|                      |                          | The King of the Dead |                            | Shelob                  |                           |                          |             |                                |              |              |
|                      |                          | Radagast             |                            |                         |                           |                          |             |                                |              |              |

We can see here how the communities are divided among the different races of middle earth. Communities 4 and 9 include mostly men. Communities 1 and 6 have mostly Hobbits, Community 3 is the Elvish one. Some communities, such as 5 and 2 seem to be more of a mix. That happens due to the battles and adventures throughout the story, forming connections appearing on the wikipages. A few characters seem to be very unconnected to other, and form a single person group.

So in conclusion, there are large communities including mainly a single race, while other communities are mixed.
In the confusion Matrix below we are able to see the rece division among the communities.

#### Confusion Matrix

![alt text](./assets/confusing_confusion_matrix.PNG "Confusion Matrix")

## 6 - Sentiment analysis and Text Analysis

### 6.1 - Sentiment analysis over characters

For the characters we performed a sentimental analysis over each of their words in the movies and calculated the score. 

![alt text](./assets/lotr_sent_total.png "Ranking for characters who appears in the three movies")

High score indicated that Bilbo, Barliman and Treebeard were the nicest people throughout the movies. Other hobbits such as Merry and Pippin also score highly. It was surprising for us to see Legolas ranked fourth from bottom, but we believe that his frequent involvement in battles contributed with his low scores. Eomer is ranked lower than him, at the bottom, confirming our expectations of evil persons, we can see the two of Gríma and Gothmog, who are evil characters.

Some other surprising results show Saruman in the middle of the pack, but in the beginning of the movie he played a good guy when speaking to Gandalf, raising his score.

Below we can see wordclouds for Bilbo and Saruman

> Wordclouds are images containing the words that characters are more frequently saying. The size of the word depends of number of time it is pronounced.

![alt text](./assets/wordclouds/bilbo_wc.png "Most frequent words for Bilbo")

![alt text](./assets/wordclouds/saruman_wc.png "Most frequent words for Saruman")

### 6.2 - Evolution of sentiments over the books

Thanks to the sentiment analysis we performed we are able to know when the darkest and happiest time of the story occur.

![alt text](./assets/sentiment.png "Evolution of sentiments through the story chapter by chapter")

To perform the sentiment analysis, we used a database of a little more than 10.000 English words, each word in this database is associated to its own sentimental score. Thanks to that, we are able to perform the sentimental analysis on chapters of the book or on what people are saying in the movies.

It is interesting to see that only 6 of the chapters have an average sentiment score higher than our database, meaning that in general the novels has a higher prevalence of words with a lower sentiment rating. However, note that the database we used has 10,222 words, while the number of words in the book is more than 500,000 words long, with multiple languages (Elvish and English) and a high number of words used infrequently in general in modern English.

#### 6.2.1 - Wordclouds of the highest and lowest sentiment scoring chapters.

The chapter with the worst sentiment ranking is The Bridge of Khazad-dum in the first novel. In the wordcloud one can see words such as 'hacked', 'blade', and 'axe'. Clearly indicating a battle. One who has either read the novels or seen the movies will know more about what's happening based on the words. 

![alt text](./assets/worst_chapter.png "Word cloud of chapter with the lowest sentiment score")

The chapter with the highest sentiment ranking is Farewell to Lorien, also in the first novel. In addition to some elvish words, we can see 'cakes' and 'drunk' in the cloud, indicatiang some sort of party.

![alt text](./assets/best_chapter.png "Word cloud of chapter with the lowest sentiment score")

Wordclouds for every single chapter are included in the appendix of the notebook. People who might not have time to read the whole book can possibly get the gist of what's happening in throughout the book simply by viewing the wordclouds.

### 6.3 - When a specific words is appearing in the story

![alt text](./assets/lexicaldispersion.png "Appearence of the names of main characters throughout the books.")

This lexical dispersion plot shows at what times characters who speak the most in the Lord of the Rings movie trilogy are mentioned in the books.

Note that for example Bilbo, who doesn't appear in the second movie, is mentioned a few times in the book.

As well as that, we can see that Madril is a character who only appears in the movies, and not in the original novels.

![alt text](./assets/wordsinmovie.png "Words mentioned by characters in each movie.")

## 7 - More details

If you are interested about how we came up to these results and you want to see our code you ca, check [this link to have access to our Explainer Notebook.](http://nbviewer.jupyter.org/github/Nab-88/social-graphs-and-interactions/blob/master/notebook/final.ipynb)
