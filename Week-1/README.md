# Solutions for Assignment 1

<br><br>

1. Which of the following condition(s) is/are sufficient to get a perfectly-secure encryption scheme?<br>
<br>a) Ensure that key-generation algorithm outputs a uniformly random key from the key space<br>
b) Ensure that the encryption algorithm is randomized<br>
c) Ensure that the key is as large as the plaintext<br>
d) None of these<br><br>
The correct answer is **d**,<br><br>
As there is no sufficient condition(s), which guarantees that an encryption scheme is perfectly-secure.<br><br><br><br><br>


2. Identify the incorrect statement(s) from the following.<br><br>
a) A scheme is COA-secure iff it is KPA-secure<br>
b) A scheme is KPA-secure iff it is CPA-secure<br>
c) A scheme is CPA-secure iff it is CCA-secure<br>
d) None of these<br><br>
The answers are **a**, **b** and **c**.<br><br> KPA attack model is more powerful than COA. So a scheme which is secure against a COA
attacker, need not be secure against a KPA attacker. Similarly, CPA attack model is more powerful than KPA. So a scheme
which is secure against a KPA attacker, need not be secure against a CPA attacker. Similarly, CCA attack model is more
powerful than CPA. Hence a scheme which is secure against a CPA attacker, need not be secure against a CCA attacker. So
the first three statements are false.<br><br><br><br><br>


3. Consider an instance of shift cipher with the probability distribution over the message space as follows: Pr[M = a] =
0.4, Pr[M = b] = 0.3, Pr[M = c] = 0.3. What is the probability that the ciphertext is ‘D’?<br><br>
a. 1/26<br>
b. 1/13<br>
c. 3/26<br>
d. None of the above<br><br>
Following the notations that we introduced during our lectures, we get that Pr[C = D] = Pr[M = a] · Pr[K = 3] +
Pr[M = b] · Pr[K = 2] + Pr[M = c] · Pr[K = 1]. Since the key-generation picks the shift (namely the key) uniformly
randomly from the set {0, . . . , 25}, we get that Pr[K = 3] = Pr[K = 2] = Pr[K = 1] = 1/26 . Hence we get that
Pr[C = D] = 1/26 · (Pr[M = a] + Pr[M = b] + Pr[M = c]), which is 1/26 .<br><br>
So the correct answer is **a**.<br><br><br><br><br>


4. Consider an instance of shift cipher with the probability distribution over the message space as follows: P[M=a] = 0.3,
P[M=b] = 0.6, P[M=c] = 0.1. Then identify the correct statement(s) from the following.<br><br>
a) Probability that the ciphertext is “D” is the same as the probability that the ciphertext is “E”<br>
b) Probability that the ciphertext is “D” is less than the probability that the ciphertext is “E”<br>
c) Probability that the ciphertext is “D” is more than the probability that the ciphertext is “E”<br>
d) Nothing can be said regarding the probability that the ciphertext is “D” and the probability that the ciphertext is “E”<br><br>
By following the computations done in the previous question, we can find that the probability that the ciphertext is ‘D’ will
be the same as the probability that the ciphertext is ‘E’, namely 1/26. <br><br>Hence the correct answer is **a**.<br><br><br><br><br>


5. Which of the following is/are valid condition(s) for a perfectly-secure encryption scheme?<br><br>
a) Pr[M = m|C = c] = Pr[M = m]<br>
b) Pr[C = c] = Pr[M = m]<br>
c) Pr[C = c|M = m] = Pr[C = c]<br>
d) None of the above<br><br>
It is easy to see that only the first condition always hold for a perfectly-secure encryption scheme.<br><br>Hence the answer is **a**.<br><br><br><br><br>