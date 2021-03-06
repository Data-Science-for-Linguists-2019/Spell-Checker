# Spell Checker Project

Ting-Wei Shen, tis50@pitt.edu, April 26, 2019  

## 0. Introduction

This project is designed to introduce the foundation of the spell checker. How does it work? The algorithm behind it. And the implementation of spell checker on ELI(English Language Institute) students. I will go through the project by analyzing the pros and cons of the spell checker that I used. Is there any limitation on the model? Then, I will tell the problems when I processed the ELI students' data. Something that I hoped at first; but, the real result that I got. Following, I will implement some linguistic analysis on my pruned data. Is there any finding in the result? How we can do the further searching on the data in the future. And my conclusion as well.  

## 1. Background

At first, I did not have any idea about the project. I wanted to design a model to measure the essay quality of second language learners. Do they have any common errors according to their native language? I want to apply my model on the data to see whether the quality of essays improve or not. So, I searched many articles about the spell checker model. First, I found that there is an implementation using recurrent neural network (RNN) as the model. From David Currie's model [here is the model](https://github.com/Currie32/Spell-Checker). I would like to know the principal behind it and give some trials on  tuning the model. However, running the data on my laptop may be over loading. It needs more computing resource to process. On the other hand, I did not have enough time to handle the environment conflict since there were many new stuffs to learn at the same time.

Then, I gave a shot on the model which was designed by Peter Norvig. [Here is the model](http://norvig.com/spell-correct.html). Thanks to the recommendation from Na-Rae. The Norvig's model, which is interpreted in a simple method on how to design it, gave me a lot of ideas on my project. The algorithm that Norvig's model is used, and the efficiency it represent, reveals a key concept on designing the model. We need to do the trade-off between the performance and the resource. Norvig's model can achieves about 80% to 90% accuracy at a processing speed of at least 10 words per second. Moreover, it does not need lots of resource to process, which is a good idea for my project.

## 2. Data sourcing

The data can be separated into two parts. One is the main part which is used for analysis from ELI students' essays. I put some example data [here](data_sample/df_eli_short.csv). The other one ([big.txt](big.txt)) is used for the language model, which is like a dictionary from concatenation of public domain book excerpts from [Project Gutenberg](http://www.gutenberg.org/wiki/Main_Page) and lists of most frequent words from [Wiktionary](https://en.wiktionary.org/wiki/Wiktionary:Frequency_lists) and the [British National Corpus](http://www.kilgarriff.co.uk/bnc-readme.html).  

## 3. Data cleanup

In the data cleanup part, I combined these three csv files into one ELI data-frame by choosing separate key indexes.

* answer.csv  
  * student_id, question_id, text
* student_information.csv
  * student_id, gender, native_language
* question.csv
  * question_id, question

The shape of data will be like (46239, 6), which contains 46239 texts with 6 attributes.  
Here is the data-frame:  

![png](image_files/part3_plot1.png)


Because of the fair use, I had to select 1/10 as the sample data; moreover, I had to remove the personal information in the texts. So I finally chosen 492 texts. Then, I did some basic analysis to go through my data. I found that the data is not distributed well, some texts are really long, some are short. Considering about the questions students were asked, they may answer just in one word. For example, "choose one word that matches the definition here." This kind of question and answer would add a lot of bias in my analysis, I had to eliminate these bias.

Here is the link to my Jupyter notebook [3. Data cleanup](https://nbviewer.jupyter.org/github/Data-Science-for-Linguists-2019/Spell-Checker/blob/master/ELI_data_frame_part1.ipynb#Loading-chosen-data).


### 3.1 Text length as token count  

- I need to set some filter when I choose the data.

In this case, I narrowed down my file in the word counts from 50 to 600. Since there are almost 65% of text files is lower than 65 tokens (about 10% are 1 word texts); after the filtering, there are only 130 texts left. It is not an easy task to balance the privacy and the data I need. If I wanted better analysis result, I needed to examine more original students' essays; however, I did not have that much time and the performance may not increase as much as I expected. I decided to keep going to next parts and completed the prototype of my project.  

- Here is the tokens distribution of my data:

![png](image_files/part1_plot1_2.png)

Here is the link to my Jupyter notebook [3.1 Text length as token count](https://nbviewer.jupyter.org/github/Data-Science-for-Linguists-2019/Spell-Checker/blob/master/ELI_data_frame_part1.ipynb#1.-Text-length-as-token-count).

### 3.2 Value count by native language

- Let's do some data analysis by students' native languages.

If we took a look at the native languages' distribution, we can easily find that the texts classified by native languages are not distributed well. About 59% texts are from Arabic, Korean and Chinese. The analysis we had to focus on will be in these three main categories.

- Here is the value count by native language of my data

![png](image_files/part1_plot2_2.png)

Here is the link to my Jupyter notebook [3.2 Value count by native language](https://nbviewer.jupyter.org/github/Data-Science-for-Linguists-2019/Spell-Checker/blob/master/ELI_data_frame_part1.ipynb#2.-Value-count-by-native-language).

## 4. Analysis
In this part, I am focusing on linguistic analysis of the dataset. I separate the analysis into three parts - Lexical diversity, Syntactic complexity and Vocabulary level. I drop text length analysis because text length is not distributed well. Some texts are really long and some are short. Because students are asked by different questions, this result is reasonable. At first, I set the text length between 50 to 600 tokens, in case of omitting too much data. Then, I plot the native language and gender distribution chart. From the chart, we can find that most students' native language are Arabic, Korean and Chinese. The data from other native languages is too small to represent. The reality is that the wild data is not as plentiful as I thought. How about the gender distribution? Fortunately, the gender is distributed well for male - 70 texts and female - 62 texts. We can still do some basic analysis.

Here is the link to my Jupyter notebook [Select proper data](https://nbviewer.jupyter.org/github/Data-Science-for-Linguists-2019/Spell-Checker/blob/master/ELI_part2.ipynb#Select-proper-data).

- Here is the value count by native language of my data after filtering (50 to 600 tokens)

![png](image_files/part2_plot1.png)

- And the number of texts by gender:

![png](image_files/part2_plot2.png)

Following, the lexical diversity (take TTR as example) shows that Chinese may intend to use more types of words than Korean and Arabic. Female students may be used to utilizing more different words.
The Jupyter notebook for [1. Lexical diversity](https://nbviewer.jupyter.org/github/Data-Science-for-Linguists-2019/Spell-Checker/blob/master/ELI_part2.ipynb#1.-Lexical-diversity).

- Here is the lexical diversity chart by native languages:

![png](image_files/part2_plot3.png)

- Here is the lexical diversity chart by gender:

![png](image_files/part2_plot4.png)

For syntactic complexity, the sentence average length order is Korean, Arabic and Chinese. Korean intend to make longer sentences. If we set the classification by gender, the difference is not obvious.
The Jupyter notebook for [2. Syntactic complexity](https://nbviewer.jupyter.org/github/Data-Science-for-Linguists-2019/Spell-Checker/blob/master/ELI_part2.ipynb#2.-Syntactic-complexity).

- Here is the syntactic complexity chart by native languages:

![png](image_files/part2_plot5.png)

- Here is the syntactic complexity chart by gender:

![png](image_files/part2_plot6.png)

For vocabulary level, Chinese intend to use longer words. The gender difference in average word length is not obvious. On the other hand, the average vocabulary band order is Korean, Chinese and Arabic. Korean tend to write more sophisticated words. For gender classification, female students tend to write more sophisticated words.
The Jupyter notebook for [3. Vocabulary level](https://nbviewer.jupyter.org/github/Data-Science-for-Linguists-2019/Spell-Checker/blob/master/ELI_part2.ipynb#3.-Vocabulary-level).

- Here is the average word length chart by native languages:

![png](image_files/part2_plot7.png)

- Here is the average word length chart by gender:

![png](image_files/part2_plot8.png)

- Here is the top most frequent English words chart by native languages:

![png](image_files/part2_plot9.png)

- Here is the top most frequent English words chart by gender:

![png](image_files/part2_plot10.png)

Let's look at the spell checker part. The spell checker (by Peter Norvig) still has many restriction on data. The performance will be influenced by the dictionary and tokenized words. We need to choose the proper dictionary corresponding to our data.
The Jupyter notebook for [Apply spell checker](https://nbviewer.jupyter.org/github/Data-Science-for-Linguists-2019/Spell-Checker/blob/master/ELI_part2.ipynb#Apply-spell-checker).

- Here are the examples of mis-recommendations:

![png](image_files/part2_plot11.png)

![png](image_files/part2_plot12.png)

On the other hand, this model may be more suitable to the speaking data which are written as the texts. The data from speaking may contains more spelling error than writing materials.  

## 5. Conclusion
Although the result is not as good as I thought at first. I still regard that it is worth to do these preliminary trials. In the future, I can try more data from the speaking material rather than written essays, since people may have more spelling errors in speaking. In the writing essays, people can check spelling errors when they were typing, or before they submit the essays. These data will have higher accuracy, my data also reflects this situation. However, for speaking, people do not have these benefits. The accuracy may decrease at the same time. It is worth to do these kind of searching. Moreover, the model now is only based on the single word. In the modern business modules now, they can detect bi-gram and the tense, then give back the better recommendations. At the same time, it is needed to have more resource to handle the computation.  
