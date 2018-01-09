# Machine Learning

![](https://imgs.xkcd.com/comics/machine_learning.png)

## Brief Introduction

Machine learning, also called **artificial intelligence**, is a huge field of study composed of algorithms and techniques that learn from and make predictions on data. Machine learning is very much in vogue today as datasets and computing power have grown large enough to make many ML and AI techniques useful in academia and industry.

Many companies are being built on machine learning (such as the one Dr. Hagen is know part of), and this is creating a large demand for data scientists. Many people can plug data into algorithms from public codes, but that doesn't mean they understand what's going on inside the algorithms. Data science is an interesting and lucrative field, but it requires a solid foundation in linear algebra, statistics, and programming, along with a good basis of research techniques and experience. Guiding students to develop all these various disciplines is important if they would like to go into data science as a career.

Machine learning ranges from analysis of twitter to transits and data from the sea to the stars. Helping students to become data scientists is less about them mastering many techniques and more about them knowing enough to teach themselves what they need to learn for a new situation. Dr. Hagen started a data science job in August and went from working on high redshift galaxies to spending most of his time working on natural language processing and convolutional neural nets for images. He didn't know either of these beforehand, but the foundation of stats, math, and programming was essential to be able to learn them quickly.

## Supervised and Unsupervized learning
One way to divide types of machine learning tasks is between supervised and unsupervised learning. Supervised learning uses training sets of labelled data to teach the algorithms what to look for. For example, you may want to have an automated way to classify stars or galaxies based on spectra; you could use a portion of the SDSS spectra database to train the model before giving it unlabelled data. 

Unsupervised learning leaves the algorithm to find structure in the data. This is useful when labelled data don't exist or when the goal is to find patterns and features in the data.


## Types of ML Tasks
* Clustering -- given a dataset clustering analyses answer questions such as: how many clusters are there? how big are they? Which data fall in what clusters? In astronomy, this could be used for finding structure in clustering of galaxies, star forming regions, or any other such space.
* Classification -- Divide input data into two or more classes. This can be done via supervised or unsupervised methods. Classification problems range from email spam detection to astronomy spectra classification to rating the quality of images or videos online.
* Regression -- There are a whole host of machine learning regression techniques, from expansions of usual chi-square techniques such as ridge regression to using neural nets. 
* Dimensionality Reduction -- High dimensionality data is really hard to handle as its difficult to know what is important so much of original data can be ignored during analysis. That may sound scary, but in many cases this is the only way to make large sets of high dimensional data possible to analyze. 

## Tools for machine learning
* Linear algebra -- machine learning is built on linear algebra and understanding ML algorithms requires a good foundations of linear algebra.
* Statistics -- A good foundation of statistics is also absolutely necessary for understaning ML and AI techniques. Familiarity with both frequentist and bayesian techniques is important. 
* Python and the standard scientific libraries (numpy, scipy, pandas, & matplotlib). There are conservatively [50+ python libraries dedicated to ML and AI techniques](http://scikit-learn.org/stable/related_projects.html) and it would be impossible to cover them all here. I'll highlight two of the most popular libraries below.
	* [scikit-learn](http://scikit-learn.org/stable/) -- great library full of techniques with a fairly consistent API, meaning that most functions take in the same kind of data. This makes exploration of various techniques fairly straightforward.
	* [keras](https://keras.io/) -- keras makes doing deep learning as easy as it can be. It has revolutionized how deep neural nets are made, trained, and run in production. The actual computations in keras are done by other neural net libraries (generally [tensorflow](https://www.tensorflow.org/)), but its interface is straightforward and easy to use. It even has the most population convolutional neural nets built it, so you can train image recognition on your data in an afternoon or less. Public convolutional nets can solve problems such this straight out of the box:![](https://imgs.xkcd.com/comics/tasks.png) 
* R -- statisticians language of choice. Some obscure or very new techniques may only be available in R.
* Cloud computing -- All major cloud computing providers have pre-built images features most of the ML software you need, so its straightforward to spin up as many processes as you desire. 

## Some ways to explore ML in the classroom
* scikit-learn has great [tutorials](http://scikit-learn.org/stable/tutorial/basic/tutorial.html) and [examples](http://scikit-learn.org/stable/auto_examples/index.html) that teach you techniques step by step.
* Neural Nets -- there are many keras tutorials available. [This one](http://cv-tricks.com/tensorflow-tutorial/keras/) is good. However, there is a large nomenclature in neural nets and it would take a couple weeks of classroom data to teach. [Goodfellow and Bengio's *Deep Learning*](http://www.deeplearningbook.org/) is a great text for a class or personal learning.

## Questions
Please feel free to contact Dr. Hagen at alex.hagen.phd@gmail.com for any questions about ML, or how to include it in the classroom. I'm also very happy to chat with students about careers in data science or related subjects.