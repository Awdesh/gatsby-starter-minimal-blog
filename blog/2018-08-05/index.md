---
date: "2018-08-05"
cover_image: https://thepracticaldev.s3.amazonaws.com/i/qc66bf5l0clyx6fy0fsk.jpeg
title: Shuffling algorithms and randomization to improve algorithm‘s runtime.
category: Coding, Programming, Computer science, java
---

Shuffling cards is an essential part of every card game. There are many techniques for shuffling cards but overhand and riffle are the most popular ones.

**Overhand shuffle**

In this shuffle a set of cards are transferred from bottom of the deck to the top of the deck and the same process gets executed recursively.

![overhand shuffle](https://thepracticaldev.s3.amazonaws.com/i/j45nr8lkzklnhg1rbb95.jpg) 
                              

A deck of cards is essentially a fixed sized array of length 52. Overhand shuffle puts set of cards from the end of the array to the beginning of array. This process gets repeated to get a good shuffle.

**Riffle shuffle**

This involves cutting the deck into 2 halves so we get two set of cards and riffle them such that at the end both half gets interleaved.

![riffle shuffle](https://thepracticaldev.s3.amazonaws.com/i/5lczb2w52vh9gxjm12uo.gif)

A quick implementation of riffle shuffle would be something like following.

![kata](https://thepracticaldev.s3.amazonaws.com/i/nzcyu61qvv7cup6kx3k5.png)

There are shuffling algorithms in existence that runs faster and gives consistent results. These algorithms relies on randomization to generate a unique random number on each iteration.

As per wikipedia

> If a computer has access to purely random numbers, it is capable of generating a "perfect shuffle".

**Fisher-Yates** shuffle is one such algorithm for achieving a perfect shuffle using random number generator. Algorithm is named after Ronald Fisher and Frank Yates who first described this algorithm in their book in 1938. Later Donal Knuth and Richard Durstenfeld introduced improved version of the algorithm in 1964. 

Unlike swapping items at two different index, algorithm generates a random number k between range of the elements inside an array. Every iteration updates the last element in the range thus random generator works on new range on every iteration and generates a unique number every time.


```       
        Random rnd = new Random();
        for (int i = ar.length - 1; i > 0; i--)
        {
           int index = rnd.nextInt(i + 1);
            // Simple swap
            int a = ar[index];
            ar[index] = ar[i];
            ar[i] = a;
            
        }

```

Above algorithm works in linear time and faster than riffle shuffle. Putting some timing around both shuffle algorithm for an array of 100 integers produces below result.

```
**************
Riffle Shuffle
***************
Time Taken is-: 45298827
***************

***************
Knuth Shuffle
**************
Time Taken is-: 1325950

```

Programming languages use similar algorithm in their inbuilt implementation of shuffle method. Java's implementation of shuffle method could be used by invoking

```
collections.shuffle()
```

To shuffle a linked list which doesn't not allow access of object by their index, Java converts it back to array first so to have random access, shuffles it and converts it back to list.

Shuffle method's implementation From Java docs


```
  private static final int SHUFFLE_THRESHOLD = 5;
  if (size < SHUFFLE_THRESHOLD || list instanceof RandomAccess) {
            for (int i=size; i>1; i--)
                swap(list, i-1, rnd.nextInt(i));
        } else {
            Object arr[] = list.toArray();
            // Shuffle array
            for (int i=size; i>1; i--)
                swap(arr, i-1, rnd.nextInt(i));
            ...
  
```

###Can randomization improve runtime of an algorithm.

A good shuffling algorithm has a function which generates a unique random number consistently. Quick sort which gives quadratic time performance on sorted array can generate consistent O(nlogn) result by randomizing sorted array first and then fed it into quick sort algorithm. 

There are two different types of randomization algorithms namely **Las Vegas** and **Monte Carlo** algorithms. IMHO, one can't get a better name than Las Vegas for a shuffling algorithm :)

__Las Vegas__ algorithm guarantees to give result in expense of the time complexity whereas __Monte Carlo__ compromises guarantee of result by exiting early if it doesn’t find the desired output. If we have to search an item inside an array Las Vegas algorithm will execute until it finds the expected item whereas Monte Carlo will execute for couple of cycles and stops if it doesn't find the item. Rabin Karp algorithm for string searching uses Las Vegas algorithm to find all matching sub-string inside input string.

###Applications

Randomized algorithms are useful in applications that requires good results consistently irrespective of input to the algorithms. Software in rockets, satellites, airplane, cryptography utilizes randomization to get high probability of good result on algorithm

###Resources

https://en.wikipedia.org/wiki/Fisher%E2%80%93Yates_shuffle
https://www.geeksforgeeks.org/randomized-algorithms-set-2-classification-and-applications/

Images are taken from google.


###Conclusion

There is so much to learn and write about shuffling algorithms  and randomization. In my next post, we'll sort back cards after shuffling them in here using inbuilt sort function in language. 

Stay tuned :)

Home About Sustaining Membership Privacy Policy Terms of Use Contact Code of Conduct DEV Community copyright 2018 🔥

```js
(function() {

var cache = {};
var form = $('form');
var minified = true;

var dependencies = {};

var treeURL = 'https://api.github.com/repos/PrismJS/prism/git/trees/gh-pages?recursive=1';
var treePromise = new Promise(function(resolve) {
	$u.xhr({
		url: treeURL,
		callback: function(xhr) {
			if (xhr.status < 400) {
				resolve(JSON.parse(xhr.responseText).tree);
			}
		}
	});
});
```

Zwei flinke Boxer jagen die quir

```md
# asdfasdfads
- auesufuaus
```

```css
code[class*="language-"],
pre[class*="language-"] {
	color: black;
	background: none;
	font-family: Consolas, Monaco, 'Andale Mono', 'Ubuntu Mono', monospace;
	text-align: left;
	white-space: pre;
	word-spacing: normal;
	word-break: normal;
	word-wrap: normal;
	line-height: 1.5;

	-moz-tab-size: 4;
	-o-tab-size: 4;
	tab-size: 4;

	-webkit-hyphens: none;
	-moz-hyphens: none;
	-ms-hyphens: none;
	hyphens: none;
}
```