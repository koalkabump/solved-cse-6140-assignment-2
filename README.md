Download Link: https://assignmentchef.com/product/solved-cse-6140-assignment-2
<br>



<h1>1           Scheduling with Weights</h1>

The deadline for homework 1 is upon us. The TA sits in front of the computer, with a mountain of emails from students with doubts. Say we have a set of <em>n </em>emails to answer, where each email <em>j </em>requires time <em>t<sub>j </sub></em>to answer, and has an importance <em>w<sub>j </sub></em>that represents how urgent it is (higher weight means more urgent). We want to find an order to schedule the replies that gives precedence to writing critical emails sooner. Formally, let <em>C<sub>j </sub></em>denote the completion time of email <em>j</em>. For example, if the first three emails to write are <em>i</em>, <em>j</em>, and <em>k </em>(in that order), we would have that <em>C<sub>i </sub></em>= <em>t<sub>i</sub></em>, <em>C<sub>j </sub></em>= <em>t<sub>i </sub></em>+ <em>t<sub>j </sub></em>, and <em>C<sub>k </sub></em>= <em>t<sub>i </sub></em>+ <em>t<sub>j </sub></em>+ <em>t<sub>k</sub></em>. Our goal is to find an order to schedule the replies that minimizes.

As it turns out, this problem has a similar solution to the <em>Minimizing Max Lateness </em>problem we solved in class. Specifically, if we sort the jobs based on the correct criteria, our schedule will be optimal. For each of the following criteria, either give a small example showing it does not always produce an optimal schedule, or give a proof of correctness based on the exchange argument (following the framework we used for minimizing max lateness, i.e. show that swapping two adjacent out-of-order emails in a schedule only improves the objective).

<ol>

 <li>Greedy by smallest time <em>t<sub>i </sub></em></li>

 <li>Greedy by largest weight <em>w<sub>i </sub></em></li>

 <li>Greedy by largest weight-per-unit-time first (break ties by index of emails, i.e. if two emails have the same ratio then choose the one with smaller index).</li>

</ol>

<h1>2           Divide and Conquer</h1>

Let <em>T </em>be a table of <em>n </em>relative integers. We want to find the maximum sum of contiguous elements, namely, two indices <em>i </em>and <em>j </em>(1 ≤ <em>i </em>≤ <em>j </em>≤ <em>n</em>) that maximize

<table>

 <tbody>

  <tr>

   <td>∑</td>

  </tr>

 </tbody>

</table>

<em>j k</em>=<em>i </em><em>T</em>[<em>k</em>].

<ol>

 <li>If the values in the table are <em>T</em>[1] = 2<em>,T</em>[2] = 18<em>,T</em>[3] = −22<em>,T</em>[4] = 20<em>,T</em>[5] = 8<em>,T</em>[6] = −6<em>,T</em>[7] = 10<em>,T</em>[8] = −24<em>,T</em>[9] = 13, and <em>T</em>[10] = 3, can you return the two indices and the corresponding optimal sum?</li>

 <li>Design an algorithm that return the maximum sum of contiguous elementswith a divide-and-conquer algorithm.</li>

 <li>Bonus: Design a linear-time algorithm that solves the problem through a</li>

</ol>

single scan of the array.

<h1>3           Master Theorem</h1>

For each of the following recurrences, give the asymptotic solution if the recurrence can be solved with Master Theorem. Otherwise, briefly explain why Master Theorem is not applicable.

a)

b)

c)

d)

e)

<h1>4           Dynamic Programming</h1>

Barry Cage is developing a new Search engine, Boogle, and beta testing has shown that many users hastily enter queries that do not have spaces between words, like “herecomesthesun” and “javatutorials”. So, Barry needs your help in writing an efficient algorithm to perform string segmentation. Now there are several possible segmentations of the string “herecomesthesun”, such as “here comes the sun” or “her eco me st hesun”. One possible solution would be to maximize the cumulative quality/plausibility of the individual segmented words.

Thanks to some open source code, he already has access to a function that computes the plausibility of words. Given a string of letters <em>x </em>= <em>x</em><sub>1</sub><em>x</em><sub>2</sub><em>…x<sub>k</sub></em>, <em>plausibility</em>(<em>x</em>) returns a number that can be either positive, or negative; larger numbers indicate more plausible English words (so <em>plausibility</em>(‘sun’) would be positive, while <em>plausibility</em>(‘hesun’) would be negative). The value of <em>plausibility</em>(<em>x</em>) is defined for any string of characters.

Given a long string of letters <em>y </em>= <em>y</em><sub>1</sub><em>y</em><sub>2</sub><em>…y<sub>k</sub></em>, a segmentation of <em>y </em>is a partition of its letters into contiguous blocks of letters; each block corresponding to a word in the segmentation. The total plausibility of a segmentation is determined by adding up the plausibility scores of each of its blocks. For example, the plausibility of the segmentation “here comes the sun” of the string “herecomesthesun” is equal to <em>plausibility</em>(‘here’) + <em>plausibility</em>(‘comes’)+ <em>plausibility</em>(‘the’) + <em>plausibility</em>(‘sun’).

Give and analyze a polynomial time algorithm that takes a string <em>y </em>and computes a segmentation of maximum total plausibility, <em>MaxPlausibility</em>(<em>y</em>). (One call to the function <em>plausibility</em>(<em>x</em>) can be considered as a single computational step.) Follow these steps:

<ol>

 <li>prove that the problem has optimal substructure</li>

 <li>write a recursive expression for <em>MaxPlausibility</em>, specifying the base cases and the goal</li>

 <li>write a recursive algorithm with memoization, and analyze its time andspace complexity</li>

 <li>derive a valid order in which subproblems can be evaluated bottom-up,and write the iterative (bottom-up) version of your algorithm.</li>

</ol>