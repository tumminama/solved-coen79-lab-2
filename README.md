Download Link: https://assignmentchef.com/product/solved-coen79-lab-2
<br>
Sub-Project 1:<strong> Statistician </strong>

<strong> </strong>

Specify, design, and implement a class called statistician.

After a statistician is initialized, it can be given a sequence of double numbers. Each number in the sequence is given to the statistician by activating a member function called next.

For example, we can declare a statistician called s, and then give it the sequence of numbers 1.1, –2.4, 0.8 as shown here:




statistician s;

s.next(1.1);

s.next(-2.4);

s.next(0.8);




After a sequence has been given to a statistician, there are various member functions to obtain information about the sequence.




<ul>

 <li>Name the class “statistician” with all lowercase letters.</li>

 <li>The function “next” should add a number to the sequence.</li>

 <li>The function “length” should return the number of values in the sequence.</li>

 <li>The function “sum” should return the sum of the numbers in the sequence.</li>

 <li>The function “mean” should return the mean of the numbers in the sequence.</li>

 <li>The function “minimum” should return the smallest number in the sequence.</li>

 <li>The function “maximum” should return the largest number in the sequence.</li>

 <li>The function “reset” should erase the sequence.</li>

</ul>




Notice that the length and sum functions can be called at any time, even if there are no numbers in the sequence. In this case of an “empty” sequence, both length and sum will be zero. But the other member functions all have a precondition requiring that the sequence is non-empty.

You should also provide a member function that erases the sequence (so that the statistician can start afresh with a new sequence).

<strong>Notes</strong>: Do not try to store the entire sequence (because you don’t know how long this sequence will be). Instead, just store the necessary information about the sequence: What is the sequence length? What is the sum of the numbers in the sequence? What are the last, smallest, and largest numbers? Each of these pieces of information can be stored in a private member variable that is updated whenever next is activated.

In addition to the above functions, add the following to your documentation and implement them:

// <strong>NON-MEMBER functions for the statistician class: </strong>

//   <strong>statistician operator +(const statistician&amp; s1, const statistician&amp; s2)</strong> //     Postcondition: The statistician that is returned contains all the

//     numbers of the sequences of s1 and s2.

//   <strong>statistician operator *(double scale, const statistician&amp; s) </strong>

//     Postcondition: The statistician that is returned contains the same //     numbers that s does, but each number has been multiplied by the

//     scale number.

//   <strong>bool operator ==(const statistician&amp; s1, const statistician&amp; s2) </strong>

//     Postcondition: The return value is true if s1 and s2 have the zero

//     length. Also, if the length is greater than zero, then s1 and s2 must //     have the same length, the same  mean, the same minimum,  //     the same maximum, and the same sum.







<h1>§ Sub-Project 2: Pseudorandom number generator</h1>

<strong> </strong>

In this project you will design and implement a class that can generate a sequence of <strong>pseudorandom </strong>integers, which is a sequence that appears random in many ways.

The approach uses the <strong>linear congruence method</strong>, explained here. The linear congruence method starts with a number called the <strong>seed</strong>. In addition to the seed, three other numbers are used in the linear congruence method, called the <strong>multiplier</strong>, the <strong>increment</strong>, and the <strong>modulus</strong>. The formula for generating a sequence of pseudorandom numbers is quite simple. The first number is:

(multiplier * seed + increment) % modulus

This formula uses the % operator, which computes the remainder from an integer division.

Each time a new random number is computed, the value of the seed is changed to that new number. For example, we could implement a pseudorandom number generator with multiplier = 40, increment = 725, and modulus = 729. If we choose the seed to be 1, then the sequence of numbers will proceed as shown here:  First number

= (multiplier * seed + increment) % modulus

= (40 * 1 + 725) % 729 
= 36

and 36 becomes the new seed.




Next number

= (multiplier * seed + increment) % modulus  = (40 * 36 + 725) % 729

= 707
 and 707 becomes the new seed.




Next number

= (multiplier * seed + increment) % modulus

= (40 * 707 + 725) % 729

= 574
 and 574 becomes the new seed, and so on.

These particular values for multiplier, increment, and modulus happen to be good choices. The pattern generated will not repeat until 729 different numbers have been produced. Other choices for the constants might not be so good.

For this project, <strong>design and implement a class</strong> that can generate a pseudorandom sequence in the manner described. The initial seed, multiplier, increment, and modulus should all be parameters of the constructor. There should also be a member function to permit the seed to be changed, and a member function to generate and return the next number in the pseudorandom sequence.

<ul>

 <li>Name the class rand_gen</li>

 <li>The order of the parameters for the constructor of rand_gen should be: seed, multiplier, increment, and then modulus</li>

 <li>Name the function to generate the next number “next”.</li>

 <li>Name the function to change the value of the seed “set_seed”.</li>

</ul>