## Euler's Totient Function

Euler's Totient function returns the number of positive integers less than or equal to n which are co-prime with n. Two numbers are co-prime when they have no common divisors or their gcd is 1. For instance, 
 **phi(8)=4** , since there's four integers 1,3,5,7 that are co-prime with 8. Prime numbers are co-prime with any number below it. if P is a prime number then **phi(P)=P-1** . For instance **phi(7)=6** , since 1,2,3,4,5,6 all are co-prime with 7. 
 Phi function is also multiplicative. That means if n=a*b , then,

**Phi(n) = Phi(a * b) = Phi(a) * Phi(b)**

if a and b are not relatively co-prime then

**Phi(n) = Phi(a * b) = Phi(a) * Phi(b) * d/phi(d) , where d=gcd(a,b)**

P1 and P2 are prime numbers and n can be represented in the form of n=P1*P2, then

**Phi(n) = Phi(P1 * P2) = Phi(P1) * Phi(P2) = (P1-1) * (P2-1)**
for instance , 21 = 3 * 7

               Phi(21)=Phi(3) * Phi(7)
               
                      =(3-1) * (7-1)
                      
                      =2 * 6
                      
                      =12
                      
There are exactly 12 numbers below 21 that are Co-prime with 21.

Another important characteristics of Phi function is :
#### Summation of all the Phi of divisors of n is equal to n

If N has 4 divisors d1,d2,d3 and d4 then
Phi(d1) + Phi(d2) + Phi(d3) + Phi(d4) = n

     for instance, n = 12 has 6 divisors: 1 , 2 , 3 , 4 , 6 , 12
     so , Phi(1) + Phi(2) + Phi(3) + Phi(4) + Phi(6) + Phi(12)
         = 1 + 1 + 2 + 2 + 2 + 4
         = 12 , which is equal to n
         
#### Calculating Phi
if P is a prime number and a number n can be represeted by n=P^k . Then, There are P^k/P or P^(k-1) integers That devides P. so, there is n-P^(k-1) integers that can't be devided by P or they are co-prime with P^K.


              Phi(n)=Phi(P^k)
              
                    =n-P^(k-1)
                    
                    =P^k - P^(k-1)
                   
If  n = P1^a1 * P2^a2 * P3^a3 ................ Pk^ak , where P1,P2....Pk are prime numbers then , We can say that

      Phi(n) = Phi(P1^a1) * Phi(P2^a2) .......... Phi(Pk^ak)
      
             = ( P1^a1 - P1^(a1-1) ) * (P2^a2 - P2^(a2-1) ) ......... ( Pk^ak - Pk^(ak-1) )
             
             = ( P1^a1 - P1^a1/P1 ) ) * (P2^a2 - P2^a2/P2 ) ) ......... ( Pk^ak - Pk^ak/Pk) )  [a^(b-1) = a^b/a ]
             
             = P1^a1 ( 1-1/P1 ) P2^a2 ( 1-1/P2 ) .........Pk^ak( 1-1/pk)
             
             = P1^a1 * P2^a2 .....Pk^ak * ( 1-1/P1 )( 1-1/P2 ).........( 1-1/pk)
             
             = n * ( 1-1/P1 )( 1-1/P2 ).........( 1-1/pk)

A simple source code in cpp can be found [here](https://github.com/raihankhan/DATA-STRUCTURE-AND-ALGORITHMS/blob/master/Number%20Theory/Euler's%20Phi.cpp)

#### calculationg Phi for all numbers less than or equal to n

Below is complete algorithm:

1) Create an array phi[1..n] to store Φ values of all numbers 
   from 1 to n.  

2) Initialize all values such that phi[i] stores i.  This
   initialization serves two purposes.
   a) To check if phi[i] is already evaluated or not. Note that
      the maximum possible phi value of a number i is i-1.
   b) To initialize phi[i] as i is a multiple in above product
      formula. 

3) Run a loop for p = 2 to n
    a) If phi[p] is p, means p is not evaluated yet and p is a 
       prime number (slimier to Sieve), otherwise phi[p] must 
       have been updated in step 3.b
    b) Traverse through all multiples of p and update all 
       multiples of p by multiplying with (1-1/p).

4) Run a loop from i = 1 to n and print all Ph[i] values.
[collected](https://www.geeksforgeeks.org/eulers-totient-function-for-all-numbers-smaller-than-or-equal-to-n/)

A simple source code in cpp can be found [here](https://github.com/raihankhan/DATA-STRUCTURE-AND-ALGORITHMS/blob/master/Number%20Theory/Euler's%20Phi%20of%20all%20numbers.cpp)

#### For multiple queries we can calculate all the prime numbers requied using a seive of eratostenes and then calculate phi for each query. [This](https://github.com/raihankhan/DATA-STRUCTURE-AND-ALGORITHMS/blob/master/Number%20Theory/Euler's%20Phi%20for%20multiple%20queries(optimized).cpp) is a simple source code illustration.  

                    

