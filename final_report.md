# Spell Checker Project

Ting-Wei Shen, tis50@pitt.edu, April 26, 2019  

## 0. Introduction
This project is designed to introduce the foundation of the spell checker. How does it work? The algorithm behind it. And the implementation of spell checker on ELI(English Language Institute) students. I will go through the project by analyzing the pros and cons of the spell checker that I used. Is there any limitation on the model? Then, I will tell the problems when I processed the ELI students' data. Something that I hoped at first; but, the real result that I got. Following, I will implement some linguistic analysis on my pruned data. Is there any finding in the result? How we can do the further searching on the data in the future. And my conclusion as well.  

## 1. Background
At first, I did not have any idea about the project. I wanted to design a model to measure the essay quality of second language learners. Do they have any common errors according to their native language? I want to apply my model on the data to see whether the quality of essays improve or not. So, I searched many articles about the spell checker model. First, I found that there is an implementation using recurrent neural network (RNN) as the model. From David Currie's model [here is the model](https://github.com/Currie32/Spell-Checker). I would like to know the principal behind it and give some trials on  tuning the model. However, running the data on my laptop may be over loading. It needs more computing resource to process. On the other hand, I did not have enough time to handle the environment conflict since there were many new stuffs to learn at the same time.

Then, I gave a shot on the model which was designed by Peter Norvig. [Here is the model](http://norvig.com/spell-correct.html). Thanks to the recommendation from Na-Rae. The Norvig's model, which is interpreted in a simple method on how to design it, gave me a lot of ideas on my project. The algorithm that Norvig's model is used, and the efficiency it represent, reveals a key concept on designing the model. We need to do the trade-off between the performance and the resource. Norvig's model can achieves about 80% to 90% accuracy at a processing speed of at least 10 words per second. Moreover, it does not need lots of resource to process, which is a good idea for my project.

## 2. Data sourcing
For the data





## 3. Data cleanup
... and here I am, pointing to a [particular section of my code](https://nbviewer.jupyter.org/github/Data-Science-for-Linguists-2019/Spell-Checker/blob/master/image_files/part1_plot1.png) in my Jupyter Notebook.


Note that I am linking to the jupyter nbviewer's rendered view. (Linking to the GitHub's version will be [like this](process_data.ipynb#Second-section), only that it does not work. More info in the [guildelines](https://naraehan.github.io/Data-Science-for-Linguists-2019/project#final).)   

## 4. Analysis


... Again, make sure to link to [relevant sections of your code](https://nbviewer.jupyter.org/github/Data-Science-for-Linguists-2019/Inaugural-Address-Project/blob/master/process_data.ipynb#Third-section). Plots can be embedded too, like below. Click the `Raw` button above to see my Markdown source code.

![png](image_files/output_8_0.png)



## 5. Conclusion
... ...
