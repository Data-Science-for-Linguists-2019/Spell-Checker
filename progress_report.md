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

For the data-frame, I choose a new ELI-data-frame to replace my old one. In the second report part, I combined answer.csv, student_information.csv and  question.csv to set a ELI data-frame. Because of the fair use, I have to select 1/10 as the sample data; moreover, I have to remove the personal information in the texts. So the total text I choose are 494 files. Then, I do some basic analysis to go through my data. We can find that the data is not distributed well, some texts are really long, some are short. Considering about the questions students were asked, they may answer just in one word. For example, "choose one word that matches the definition here". We may need to set some filter when we choose the data. Here is my [Jupyter notebook](https://github.com/Data-Science-for-Linguists-2019/Spell-Checker/blob/master/ELI_data_frame.ipynb).

For my project target, I am still working on employing spell checker function, and find the way to apply it on ELI students' text.

#### Sharing scheme
For the fair use, I choose 1/10 as my sample data. And remove the personal information in the texts. So the total text I choose are 494 files.

#### My license
MIT License

Copyright (c) 2019 Spell_checker

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.











## Third Progress Report (4/9/19)
