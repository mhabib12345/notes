+++
date = '2025-05-31T18:28:44+07:00'
draft = false
math = true
title = 'Describing Data'
+++

_(copied from "MathinSociety" Book)_

## Measures of Central Tendency

---

Let's begin by trying to find the most "typical" value of a data set. 
Note that we just used the word "typical" although in many cases you might think of using 
the word "average." We need to be careful with the word "average" as it means different 
things to different people in different contexts. One of the most common uses of the word 
"average" is what mathematicians and statisticians call the arithmetic mean, or just plain old 
mean for short. "Arithmetic mean" sounds rather fancy, but you have likely calculated a 
mean many times without realizing it; the mean is what most people think of when they use 
the word "average".

---

### Mean
The mean of a set of data is the sum of the data values divided by the number of 
values.

### Median
The median of a set of data is the value in the middle when the data is in order
To find the median, begin by listing the data in order from smallest to largest, or largest 
to smallest.
If the number of data values, N, is odd, then the median is the middle data value. This 
value can be found by rounding N/2 up to the next whole number. 
If the number of data values is even, there is no one middle value, so we find the mean 
of the two middle values (values N/2 and N/2 + 1)

### Quartiles
Quartiles are values that divide the data in quarters.

The first quartile (Q1) is the value so that 25% of the data values are below it; the third 
quartile (Q3) is the value so that 75% of the data values are below it. You may have 
guessed that the second quartile is the same as the median, since the median is the 
value so that 50% of the data values are below it. 

This divides the data into quarters; 25% of the data is between the minimum and Q1, 
25% is between Q1 and the median, 25% is between the median and Q3, and 25% is 
between Q3 and the maximum value

### Five number summary

The five number summary takes this form: 
Minimum, Q1, Median, Q3, Maximum

#### To find the first quartile, Q1
Begin by ordering the data from smallest to largest
Compute the locator: L = 0.25n
If L is a decimal value: 
Round up to L+
Use the data value in the L+th position
If L is a whole number:
Find the mean of the data values in the Lth and L+1th positions.

#### To find the third quartile, Q3
Use the same procedure as for Q1, but with locator: L = 0.75n

For visualizing data, there is a graphical representation of a 5-number summary called a box 
plot, or box and whisker graph. 

### Box plot
A box plot is a graphical representation of a five-number summary. 
To create a box plot, a number line is first drawn. A box is drawn from the first 
quartile to the third quartile, and a line is drawn through the box at the median. 
“Whiskers” are extended out to the minimum and maximum values. 