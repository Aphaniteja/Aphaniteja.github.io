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

Machine Learning algorithms learn from data. They learn to find statistical patterns among the training data and use those patterns to answer questions about unseen data. 

I mentioned that F is a computer program, but within F is M which is the machine learning algorithm.
A machine learning algorithm consists of a model.  A model is nothing but a set of assumptions we make about the problem. For example, the popular linear regression model assumes that output is a linear function of the input

Where do these assumptions come from?
Statisticians and computer scientists have come up with these assumptions for a long time. Actually anyone can come up with assumptions, but the validity and performance of those assumptions decide good ml model from a bad one.

Let's get back to the problem at hand. We learned that F can be built with an ML algorithm and that before we use an ML algorithm, first we need to train it with data. Data is very accessible nowadays(in general and unlabelled). But if data is not available, then we could try to build NLP systems based on rules. For example, we could classify the word which appears after the word "the" as a noun. That rule would work in our example. Since "bar" appears after "the", this program would return
us ["bar"] as the answer. But many times this program would return incorrect results. We want to minimize our errors, and ML algorithms have proven to be really good at solving NLP problems.

So we need to get data first. There are places online where one can get access to annotated parts of speech data. For example [this one.](https://github.com/teropa/nlp/tree/master/resources/corpora/treebank)

Great.Now that we have data. We can train the model. But how do we pass the data through the model though? That is the topic of the next section


### Representing text numerically
Within the machine algorithm lies the ML model. ML model is usually a mathematical function f(x). This is different from our computer program F(x). 
f(x) is just a mathematical formula, and in many cases, it is differentiable too. The domain of this function is usually the real Tensor and the output is also a real Tensor. Obviously, the function is multidimensional.

Consider our sentence X. 
X="He went to the bar"
this sentence can be represented in many ways. One way is as words. 
["He","went","to","the","bar"] . 
if we pass X through f. we should get the output [0,0,0,0,1].
The only noun is "bar"

 F(["He","went","to","the","bar"]) -> [0,0,0,0,1]

 One more way to express X could be as
['H','e',' ','w','e','n','t',' ','t','o',' ','t','h','e',' ','b','a','r'].
The outcome would still be [0,0,0,0,1] corresponding to the words. This can also be changed on how we formulate the problem. 

But f(x) only takes numerical tensor as an input. So we need to convert these words into numbers.
That is the topic of the next blog post.



