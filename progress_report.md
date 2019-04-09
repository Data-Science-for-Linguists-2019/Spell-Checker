# Progress Report

## Preliminary Report (2/7/19)
I created a GitHub repository, wrote a README document, and pushed the project plan. After the project ideas' feedback, I decided to focus on spell checker more. Then I can use this model to detect L2 learners' spelling mistakes. I need to search more articles about spell checker now; after that, I can go deeply into these field. For the data part, I choose twenty popular books from [Gutenberg](http://www.gutenberg.org) now. I hope to examine this small portion data first to help me understand the basic knowledge behind spell checker.

## First Progress Report (2/21/19)
In this part, I have completed the data acquisition process, and choose the 20 txt files from [Gutenberg](http://www.gutenberg.org) as my model training data. Here is my [Jupyter notebook](https://github.com/Data-Science-for-Linguists-2019/Spell-Checker/blob/master/spell_checker_main.ipynb). For the project goal, I want to increase the performance of the spell checker model that I reference from this [Github project](https://github.com/Currie32/Spell-Checker). I attempt to build a model and know the knowledge behind it. Here I encounter some problem is that I do not have computing resource, so I try to use Pitt CRC(center for research and computing) resource as my training machine. However, there are several environment issue need to be resolved.

#### Sharing plan
I think it is fine to share the data from The Project Gutenberg website because their copyrights have expired. I plan to share the sample one. If it is needed, I can share more data to help me explain my result.

Terms of use (from the website)

**Our eBooks may be freely used in the United States** because most are not protected by U.S. copyright law, usually because their copyrights have expired. They may not be free of copyright in other countries. Readers outside of the United States must check the copyright terms of their countries before downloading or redistributing our eBooks. We also have a number of copyrighted titles, for which the copyright holder has given permission for unlimited non-commercial worldwide use.

**The Project Gutenberg website is for human users only.** Any real or perceived use of automated tools to access our site will result in a block of your IP address. This site utilizes cookies, captchas and related technologies to help assure the site is maximally available for human users only.

## Second Progress Report (3/19/19)

For the data-frame, I choose a new ELI-data-frame to replace my old one. In the second report part, I combined answer.csv, student_information.csv and  question.csv to set a ELI data-frame. Because of the fair use, I have to select 1/10 as the sample data; moreover, I have to remove the personal information in the texts. So the total text I choose are 492 files. Then, I do some basic analysis to go through my data. We can find that the data is not distributed well, some texts are really long, some are short. Considering about the questions students were asked, they may answer just in one word. For example, "choose one word that matches the definition here". We may need to set some filter when we choose the data. Here is my [Jupyter notebook](https://github.com/Data-Science-for-Linguists-2019/Spell-Checker/blob/master/ELI_data_frame.ipynb).

For my project target, I am still working on employing spell checker function, and find the way to apply it on ELI students' text.


## Third Progress Report (4/9/19)
In this part, I am focusing on linguistic analysis of the dataset. I separate the analysis into three parts - Lexical diversity, Syntactic complexity and Vocabulary level. I drop the text length analysis because the text length is not distributed well. Some texts are really long and some are short. Because students are asked by different questions, this result is reasonable. At first, I set the text length between 50 to 600 tokens, in case of omitting too much data. Then, I plot the native language and gender distribution chart. From the chart, we can find that most students' native language are Arabic, Korean and Chinese. The data from other native languages may be too small to represent. The reality is that the wild data is not as plentiful as I thought. How about the gender distribution? Fortunately, the gender is distributed well for male - 70 and female - 62. We can still do some basic analysis. Following, the lexical diversity (take TTR as example) shows that Chinese may intend to use more types of words than Korean and Arabic. Female students may be used to utilizing more different words. For syntactic complexity, the sentence average length order is Korean, Arabic and Chinese. Korean intend to make longer sentences. If we set the classification as gender, the difference is not obvious. For vocabulary level, Chinese intend to use longer words. The gender difference in average word length is not obvious. On the other hand, the average vocabulary band order is Korean, Chinese and Arabic. Korean tend to write more sophisticated words. For gender classification, female students tend to write more sophisticated words.  

Let's look at the spell checker part. The spell checker (by Peter Norvig) still has many restriction on data. The performance will be influenced by the dictionary and tokenized words. We need to choose the proper dictionary corresponding to our data. On the other hand, this model may be more suitable to the speaking data which are written as the texts. The data may contains more spelling error than writing materials.  

My Jupyter notebook:
- Data processing: [ELI_data_frame_part1](https://github.com/Data-Science-for-Linguists-2019/Spell-Checker/blob/master/ELI_data_frame_part1.ipynb)  
- Linguistic analysis: [ELI_part2](https://github.com/Data-Science-for-Linguists-2019/Spell-Checker/blob/master/ELI_part2.ipynb)  
 
My data: [df_eli_short](https://github.com/Data-Science-for-Linguists-2019/Spell-Checker/tree/master/data_sample)
