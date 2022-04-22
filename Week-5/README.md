# Solutions for Assignment 5 <br><br>
1. Choose the option(s) that are correct for AES?<br><br>
a. AES block cipher has a 128-bit block length and uses an 128-bit key.<br>
b. AES primarily is essentially a substitution-permutation network.<br>
c. AddRoundKey, SubBytes, ShiftRows, MixColumns are the four operations that are applied in a series of four stages.<br>
d. AES block cipher is proven to be secure against computational adversary.<br><br>
The first statement is false, as there are 3 different variants of AES, with 3 different key size. The second and third statements
are true. The last statement is false, as AES/DES does not give any provable-security guarantees.<br><br>
So the answers are **b** and **c**.<br><br><br><br><br>
2. Which of the following is(are) incorrect?<br><br>
a) In a CCA attack, the adversary can ask for decryptions of any ciphertext of its choice<br>
b) The CCA-security model captures a malicious adversary<br>
c) The CCA-security model captures a passive adversary<br>
d) Providing decryption-oracle to the adversary does not provide any additional power<br><br>
The first statement is incorrect, as in the CCA indistinguishability game, the adversary can ask for the decryption of any
ciphertext of adversary’s choice, except the challenge ciphertext. The third statement is incorrect, as CCA attack models a
malicious adversary. And indeed providing decryption-oracle service to the adversary increases the power of the adversary,
as all CPA-secure schemes discussed in the course can be easily broken when taken to the CCA game. <br><br>So the answers are **a**,
**c** and **d**.<br><br><br><br><br>
3. Given Fk is a secure PRP, construction of an encryption scheme is defined as: Choose a key k ∈ {0, 1}
n at random. To
encrypt m ∈ {0, 1}
n, the cipher text is c = (c1, r), where r ∈ {0, 1}
n and c1 = Fk(m) ⊕ r. The decryption is defined as
m = F
−1
k
(c1 ⊕ r). Which of the following option(s) is/are false for the given encryption scheme?<br><br>
a) Given encryption scheme is single-message CCA secure.<br>
b) Given encryption scheme is single-message CPA secure.<br>
c) Given encryption scheme is neither CCA-secure, nor CPA-secure.<br><br>
The scheme is neither CPA-secure, nor CCA-secure. This is because by looking into the ciphertext c = (c1, r), an adversary
could learn Fk(m) for the underlying m, because Fk(m) = c1 ⊕ r. This property can be utilized by the adversary in the
CPA experiment as follows: during the training phase, adversary asks for the encryption of message m and learns Fk(m),
based on the above computations. Then in the challenge phase, it submits m' = m and m1 = m'
, where m' != m. Let c
? be
the resultant ciphertext, which is an encryption of mb. Now adversary computes Fk(mb) and by comparing it with Fk(m),
which it has learnt during the training phase, adversary can easily identify whether c
?
is an encryption of m0 or m1.<br><br>
So the answers are **a** and **b**.<br><br><br><br><br>
4. Consider a MAC construction for messages of length 2n using a secure PRF F. To authenticate a 2n-bit message m =
m1||m2, where m1 and m2 are each n-bit long, output a tag (Fk(m1), Fk(m2)), where k is a n-bit truly random PRF key.
Select the incorrect option(s) from below for the given construction.<br><br>
a) The construction is CMA-secure<br>
b) The construction is SCMA-secure<br>
c) The tag-generation algorithm is deterministic<br>
d) The tag-generation algorithm is randomized<br><br>
The construction is neither CMA-secure, nor SCMA-secure, as an adversary can easily launch a “re-ordering” attack. Let
the adversary learn the tag (t1, t2) on m = (m1||m2), where (t1, t2) = (Fk(m1), Fk(m2)). Now consider the message
m0 = (m2, m1), which is different from m. It is easy to see that the adversary can now easily compute the tag t
' = (t2, t1)
on m0 = (m2||m1). Also the tag is a deterministic function of the message and the key. <br><br>So the answers are a, b and d.<br><br><br><br><br>
5. Which of the following is/are false about Message Authentication Codes?<br><br>
a. CBC MAC can be used to generate tag for only fixed-length messages.<br>
b. Block-wise CBC MAC initialized with IV = 0n, instead of IV being the number of message blocks is insecure.<br>
c. A secure MAC maintains the privacy of the underlying message.<br>
d. A secure MAC has to be always randomized.<br><br>
The first statement is false, as we have seen in the lectures, how to get various methods of authenticating messages of arbitrary
lengths, based on CBC method. The second statement is true, as indeed the construction is insecure. Suppose the adversary
queries for tag on message “A” and gets the tag tA = Fk(A ⊕ Fk(IV)). Then it queries for the tag on on “AB”, where
B = tA; the resultant tag will be Fk(B ⊕ tA) = Fk(0n). Now the adversary can forge a tag on “ABC”, where C = Fk(0n),
where adversary has already learnt Fk(0n). It turns out that the tag on “ABC” will be Fk(C ⊕ Fk(0n)) = Fk(0n), which is
already known to the adversary. The third statement is false, as the message to be authenticated also accompany the tag. The
last statement is false, as CMA-secure MACs are deterministic. <br><br>So the answers are **a**, **c** and **d**.<br><br><br><br><br>
