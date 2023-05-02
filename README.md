Download Link: https://assignmentchef.com/product/solved-cpl-homework-6
<br>
For this and next homework, we are writing in <a href="https://en.wikipedia.org/wiki/Prolog">Prolo</a><u>​    </u><a href="https://en.wikipedia.org/wiki/Prolog">g</a><a href="https://en.wikipedia.org/wiki/Prolog">.</a><u>​</u> You can use either swipl on openlab or the web app for prolog <a href="https://swish.swi-prolog.org/">her</a>​        <a href="https://swish.swi-prolog.org/">e</a> <u>​ </u>to create a program. For the web app, download your program to your computer or save it in the cloud. For using swipl on openlab, refer to the guide <a href="https://docs.google.com/document/d/1URmgP2V9NdpYxfuleegPXCx_BJIHOP5dxPpmVc-nkBM/edit?usp=sharing">her</a><u>​        </u><a href="https://docs.google.com/document/d/1URmgP2V9NdpYxfuleegPXCx_BJIHOP5dxPpmVc-nkBM/edit?usp=sharing">e</a>.​




If you would like an example Prolog file to look over, you can refer to Dr. Klefstad’s example file  in openlab with this command:




$ cat ~klefstad/public_html/public/141/hw6/mydefs​




Implement the following relations in Prolog. Where applicable, run them backward.




<ol>

 <li>Write my_reverse which does the obvious.​</li>

</ol>




?- my_reverse([a,b,c,d], R).​

R = [d,c,b,a]

<strong> </strong>

<ol start="2">

 <li><strong> </strong>Write my_length which relates the list to its length.​</li>

</ol>




?- my_length([[a,b],[c,d],[e,f]], Y).​

<ul>

 <li>= 3</li>

</ul>




<ol start="3">

 <li>Write my_subset that takes a relation and a list. The last parameter is those in the​ list that satisfy the relation. You will need operator =.. for my_subset (read <a href="https://www.cse.unsw.edu.au/~billw/prologdict.html#univ">thi</a><u>​         </u><a href="https://www.cse.unsw.edu.au/~billw/prologdict.html#univ">s</a><a href="https://www.cse.unsw.edu.au/~billw/prologdict.html#univ">)</a><u>​ </u>. It is an equal followed by two dots.</li>

</ol>




?- my_subset(atom, [a,[b],c], Y).​

<ul>

 <li>= [a,c]</li>

</ul>

<strong> </strong>

<strong> </strong>

<ol start="4">

 <li><strong>[10]</strong> Write my_member which relates an element to a list that the list is in.​</li>

</ol>




?- my_member(a,[a,b,c]).​

Yes

?- my_member(Y,[a,b,c]).​

<ul>

 <li>= a;</li>

</ul>

Y = b;

Y = c;

No

<strong> </strong>

<ol start="5">

 <li><strong>[10] </strong>Write my_intersect that relates a list to another list. The third list is the subset of​ elements that are in both the first two lists.</li>

</ol>




?- my_intersect([a,b,c],[[c],d,b,e,a], R).​

R = [a,b]




Implement the following Prolog relations. If applicable, the relation should be able to respond to the backward query.




<strong>NOTE:</strong> ​ In writing the following Prolog predicates, you may use only these primitive functions:​

<ul>

 <li>append           not</li>

 <li>member           predicates you wrote above</li>

</ul>




<ol start="6">

 <li><strong>[20] </strong>Define the predicate compute_change(Money, Quarter, Dime, Nickle, Penny). Try​ to minimize the number of coins you should give for the first answer. (No need to test backward query, but run several tests similar to this one). You will need to use the operator “is” for this one to do an evaluation of arithmetic.</li>

</ol>




?- compute_change(33,Q,D,N,P).​

Q = 1 D = 0 N = 1 P = 3

<strong> </strong>

<strong> </strong>

<ol start="7">

 <li><strong>[15] </strong>Define the predicate compose(L1, L2, L3) such that L3 consists of the element of​ L1 and L2 interleaved in order until one of them becomes nil, and then append that non-nil list at the end.</li>

</ol>




?- compose([a,b,c],[x,y,z],L).​

L = [a,x,b,y,c,z]

?- compose([a,b,c],[x,y],L).​

L = [a,x,b,y,c]

?- compose(L1,L2,[a,b,c]).​

L1 = [] L2 = [a,b,c] ;

L1 = [a] L2 = [b,c] ;

L1 = [a,c] L2 = [b];

L1 = [a,b,c] L2 = []

<strong> </strong>

<strong> </strong>

<ol start="8">

 <li><strong>[15] </strong>Define the predicate palindrome(Base, Result). You may assume that Result is​ always an even length list. However, you must show that your answer is the only possible answer.</li>

</ol>




?- palindrome([m,a,d],R).​ R = [m,a,d,d,a,m] ; no

?- palindrome(B,[n,i,s,s,i,n]).​        B = [n,i,s] ; no




Test your program with the following test cases, i.e, if you are using swipl, you can copy them into a test.in and then do “swipl &lt; test.in”.




[“main.pl”]. % ignore this if you are using web-app prolog my_reverse([a,b,c,d], R).

my_reverse(O, [a,b,c,d]).

my_length([[a,b],[c,d],[e,f]], Y). my_subset(atom, [a,[b],c], Y).  my_member(a,[a,b,c]).

my_member(Y,[a,b,c]).

my_intersect([a,b,c],[c,b], R). my_intersect([a,b,c],[[c],d,b,e,a], R). compute_change(33,Q,D,N,P).

compute_change(182,Q,D,N,P). compose([a,b,c],[x,y,z],L). compose([a,b,c],[x,y],L). compose(L1,L2,[a,b,c]). palindrome([m,a,d],R).

palindrome(B,[n,i,s,s,i,n]).

<strong> </strong>