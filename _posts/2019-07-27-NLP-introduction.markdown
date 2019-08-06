---
layout: post
title: "NLP Introduction"
date: 2019-07-27
categories: [nlp]


---
### Introduction


![parse_tree](https://raw.githubusercontent.com/Aphaniteja/aphaniteja.github.io/master/static/img/parse_tree_27Jul1.jpg)
*Generated  with [stanford parser](http://nlp.stanford.edu:8080/parser/)  and [online syntax tree generator](http://mshang.ca/syntree/)*


Consider the sentence  "He went to the bar"

Given this sentence the field of Natural Language Processing (NLP) allows us to tackle the following tasks with respect to the given sentence:

(i) Where did he go?  
(ii)Translate this sentence to German  
(iii)Print all the nouns in this sentence  

it also allows us to tackle many other tasks (which I will discuss later in the post) 


### How to get outputs from sentences

Ok.I've said that NLP allows us to tackle various problems, but how exactly can we get the answers?

Consider a sentence x. We want a program F which will give us all the noun outputs of the sentence. 

so F(x) should return ["bar"] for the above sentence.

Building this program F is the task for NLP engineers. 


This program could be built in many ways, each with various degrees of accuracy, but recently it's being built with the help of machine learning(ML) algorithms. 

Machine learning algorithms build models from data.

```python
def train_model(model,data)
    model.train(data)
```
After the model has been built, it can then take a sentence as an input and produce and output
      
```python
def predict(model,sentence)
    nouns=model(sentence)
    return nouns
```
