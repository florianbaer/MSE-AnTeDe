---
title: "Exercises SW09"
// author: Florian Bär
// date: 19.03.2022
fontsize: 12pt
geometry: "top=2cm"
output: pdf_document
---
# Task
The task is to write a one paper report regarding the Lab9. In the first lab we were introduced to the code for a neural dependency parser introduced by the paper _"A Fast and Accurate Dependency Parser using Neural Networks"_ by Danqi Chen and Christopher Manning. The started to create dependency graphs using neural networks to define the three operations **shift**, **left arc** and **right arc**. 

# Assigments
No, you can not change the number of classes to adapt regading the number of classes as these are the classes of the algorithm to make the shift, left or right arc operations. 
I tried the following number of neurons in the hidden unit with the following results:
| Id 	| Number of Units 	| Dev UAS 	| Test UAS 	|
|----	|-----------------	|---------	|----------	|
| 1  	| 10              	| 79.11   	| 79.22    	|
| 2  	| 100             	| 87.53   	| 88.01    	|
| 3  	| 200             	| 88.56   	| 89.06    	|
| 4  	| 500             	| 89.57   	| 89.87    	|

I was surprised how much 
