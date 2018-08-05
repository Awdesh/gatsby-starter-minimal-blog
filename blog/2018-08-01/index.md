---
date: "2018-08-01"
title: Dual Pivot Quick Sort Java’s default sorting algorithm for primitive data types.
category: sorting, java, programming, algorithm 
---

What happens when we do Arrays.sort() in Java? which sorting algorithm Java uses in background? 

Since Java 7 release back in 2011, default sorting algorithm used is DualPivotQuickSort which is an enhancement over classic quick sort algorithm. 

Dual pivot quick sort is a combination of insertion sort and quick sort. Insertion sort has faster runtime when the number of elements to be sorted is small,  Double pivot quick sort uses this fact thus when the number of elements are <= 47 Java performs insertion sort under the hood. 

When input size array is larger than 47 Java uses Double pivot quick sort. As the name suggests DualPivotQuickSort algorithm picks 2 pivot instead of 1. Unlike quick sort in which we partition the array around 1 pivot, we partition the array in three parts around 2 pivots. 

1st sub array  :  items < LP
2nd sub array  :  LP <= items <= RP
3rd sub array  =:  items >= RP

**Algorithm**

LP: Left Pivot 
RP: Right Pivot

1.) Left most item in an array is taken as the left pivot and Right most item as the right pivot. 
2.) Swap Left pivot with Right Pivot if LP > RP
3.) Partition array in three sub-arrays around left and right pivot.

Once partition is done we perform above 3 steps recursively on three sub-array.

Let’s walk through an example-:

![Alt text of image](https://thepracticaldev.s3.amazonaws.com/i/n6mp5fdei3q441ycdn4y.jpg)

No need to swap pivots in above image since LP < RP. 
Now we partition the array following below schemes.

1st sub array  :  items < LP
2nd sub array  :  LP <= items <= RP
3rd sub array  =:  items >= RP

![Alt text of image](https://thepracticaldev.s3.amazonaws.com/i/a3eq0j679g59dthcw42d.jpg)

Now we have 3 sub-array over which we'll perform same steps as above. Since first two arrays have only 2 items, one will become left pivot and other will become right pivot. We'll swap left pivot with right pivot if left pivot is greater than right pivot which is not the case for first two sub- arrays.

![Alt text of image](https://thepracticaldev.s3.amazonaws.com/i/ehghis7p9tsd9g1wm4q4.jpg)

For the third sub-array as we can see in below image left pivot is greater than right pivot thus we'll swap them.

![Alt text of image](https://thepracticaldev.s3.amazonaws.com/i/g95l8m8pa9g66l0v3ov0.jpg)

Swapping pivots.
![Alt text of image](https://thepracticaldev.s3.amazonaws.com/i/6f473lb9nolxytzohalq.jpg)

We don't have any more elements in the array that we can partition further.
![Alt text of image]
(https://thepracticaldev.s3.amazonaws.com/i/13zl7hgjyjuz0tkpilhr.jpg)

![Alt text of image]
(https://thepracticaldev.s3.amazonaws.com/i/nwl0r1opeozphmvzzwby.jpg)

**References**

https://www.geeksforgeeks.org/dual-pivot-quicksort/
https://stackoverflow.com/questions/20917617/whats-the-difference-of-dual-pivot-quick-sort-and-quick-sort
http://codeblab.com/wp-content/uploads/2009/09/DualPivotQuicksort.pdf

**Conclusion**
Similarly Python uses Timsort which is a combination of insertion sort and merge sort. I’d like to read and write about different other variation of quick sort in next few days.

Stay tuned:)