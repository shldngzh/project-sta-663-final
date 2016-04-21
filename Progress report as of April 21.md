#Progress report as of April 21
## Xiaodong Zhai, Luis Guirola


We started with the idea of implementing the elastic net paper by Zou and Hastie 2005. A detailed description of this project can be found the "[abstract and heading.md](https://github.com/lguirola/sta663-Final-Project/blob/master/Abstract%20and%20headings.md)" document. So far, we have completed an extended version of this motivation, with a description of the technique and the algorithm to be implemented in the document called "[Introduction: Why elastic net?.md](https://github.com/lguirola/sta663-Final-Project/blob/master/Introduction:%20Why%20elastic%20net%3F.md)", which will be the introductory/theoretical part of our write up. 

In terms of working routine, we agreed to centralize the workflow upton github, which provides and excelend platform for interactive development, but also got used to meet about once a week to solve particular things and schedule to-do task for the week. We tried to combine efforts and peer code monitoring at each steps in order to correct errors and maximize efficiency in debugging. We agreed on a number of coding guidelines that we drafted in a document called "code-conventions.md". 

On the coding front, the current state of our work is as follows. We first proceeded to code the __coordinate descent__ algorithm for elastic net in plain Python. We ran into some complications that got us stuck in the debugging for a while. To assess the accuracy of our results, we compared them with alternative data sets -the diabetes data from  sklearn, and a simulated sparse data sets- and results obtained from other packages -from sklearn in particular. 

Once we managed to obtain satisfactory results and to wrap up the code in a function, we proceeded to the optimization step in which we are currently working. A simple comparison of the code performance with sklearn shown that ours did substantially worse 3.6/240 ms. More strikingly, compiling it with Numba did not achieve any improvement at all -we attribute this to the format of the code. These efforts can be verified in [this notebook](https://github.com/lguirola/sta663-Final-Project/blob/master/elastic_net_function_wrapper.ipynb). Starting from these points, each of us concentrated in rewriting the code in static Cython and C++, a task we are close to have achieve at the moment (the corresponding notebooks are [here](https://github.com/cliburn/sta-663-2016/blob/master/projects/FinalProjectGuide.ipynb) and [here]()