---
layout: post
title: "Got schooled"
date: 2014-02-24 15:04:03 -0600
comments: true
categories: [ruby, learning]
---

I thought I was hot stuff going through Chris Pine's [_Learn To Program_](http://pragprog.com/book/ltp2/learn-to-program) when I blitzed through the first nine chapters no problem. The exercises were a good challenge, but didn't pose too much of a threat...

And then I got to chapter ten. In ten, Chris struck a cord with me when he challenges his readers to define his or her own _sort_ method:  
> ...like the Jedi who constructs his own lightsaber, you'll exhibit a greater mastery if you write your own sorting method.

Challenge accepted! That was five days ago.

###Enter the Sorting Dragon

I tried everything I could think of, but still struggled with ultimately keeping track of my data.  I found a great analogy someone posted about treating the elements of your array like playing cards (having "sorted", "unsorted", and "active" groups of elements), and think of solving the problem that way. That was a good starting point, but I was still struggling because I couldn't find a way to selectively remove elements from the unsorted array once I had added them to the sorted array.

So, I eventually broke down and checked Chris' solution at the end of the book. Our code was identical except for one key point of logic:

#####Me:
1. Pop an element from the original array.
2. Add it to the sorted list.
3. Iterate through the remaining elements.
	* If there was an element smaller than what was already added, replace it and push the less-small element back into the unsorted pile.
4. Repeat (using array.each) until length of sorted array matched original array.

######Chris:
1. Pop an element from the original array.
2. Assign it to a local variable. Create an empty "unsorted" array.
3. Iterate through the remaning elements.
	* If there was a smaller element than what was reference by the variable, replace it and push the less-small element to the "unsorted" array.
4. Repeat (using array.each) until the variable contains the smallest element from the original array.
5. Push that smallest element into the "sorted" array, and recursively pass the "unsorted" array to the sort method until the "unsorted".length <= 0.

####Conclusion

Well, I have to give myself _some_ credit. When I saw his answer, he and I were on the same page logic-wise. But, like a math problem, the devil is in the details. I was performing an action a bit too soon and hadn't separated my logic from my action: I was adding to the sorted list and _then_ comparing instead of the other way around.

All in all, I think this was a very valuable lesson for me, that I'm not as much an "advanced beginner" as I thought I was. I'm going to try to swallow my pride (which was a bit hurt, I'll be honest), finish the exercises in the chapter, and keep learning. 

No giving up.