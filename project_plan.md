# Spell checker

Ting-Wei Shen  
tis50@pitt.edu  
Feb 7, 2019  

## Summary

This is a project to design a model to detect the sentence with  spelling mistakes and create a corrected sentence. The data that I choose now will be twenty popular books from [Project Gutenberg](http://www.gutenberg.org/ebooks/search/?sort_order=downloads)(small portion first). For analysis part, I will focus on the computational methods first, then explore more data that could improve my model performance. This idea comes from [Currie32 Github](https://github.com/Currie32/Spell-Checker).


## The DATA portion  

#### What will your data look like?  

I will use small portion data now to check the performance of the model. The data will be twenty popular books from [Project Gutenberg](http://www.gutenberg.org/ebooks/search/?sort_order=downloads). If the model works, then I will explore more suitable data.

#### What sorts of data sourcing and cleaning up effort will be involved?

I will eliminate the unnecessary information, just leave the core essay as the training data.


#### Do you have a sense of the overall data size you should be aiming for?

The overall data size will need to be determined.


#### Do you have an existing data source in mind that you can start with, and if so, what are the URLs or references?

[Project Gutenberg](http://www.gutenberg.org/ebooks/search/?sort_order=downloads).

## The ANALYSIS portion

#### What is your end goal?

1. For the end goal, I hope to design a model to detect the mistakes in the sentence, and correct them.

2. By understanding the method behind these model, we may increase the performance of spell checker.

3. We may use these model to determine the quality of different essay by different L2 learners, and correct the mistakes within the sentences.

#### Any hypothesis you will be testing?

Utilize spell checker algorithm to help me check spelling accuracy.

#### Are you planning to do any predictive analysis (machine learning, classification, etc.), and using what methods?

I am not sure using what methods now. I may try some pandas function to do data cleaning first. Then I can observe the data to figure out the method I can apply.

## The PRESENTATION portion

I may do data/analysis/presentation as 60-60-60 weight portion, and display the result by Jupyter notebook.
