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
                    

