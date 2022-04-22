# Solutions for Assignment 4 <br><br>
1. Which of the following is/are false about modes of operation?<br><br>
a) A sequence of n messages can be encrypted using block cipher by making less than n calls to a secure PRF<br>
b) Cipher-text computation is parallelizable in CTR mode.<br>
c) Plain text of any length can be encrypted in OFB mode<br>
d) Stateful variant of Counter mode is secure where as OFB mode is insecure<br><br>
The first statement is false, as we need at least n calls to the underlying PRF, for encrypting n messages. The second
statement is true: clearly in the CTR mode, the pseudo-random stream of pad can be computed in advance and in parallel
and different blocks of message can be encrypted in parallel. The third statement is true, as depending upon the length of the
plaintext, the corresponding sized pseudo-random stream can be used for XORing. The last statement is false, as the stateful
variant of both the CTR mode as well as the OFB modes are secure. <br><br>So the answers are **a** and **d**.<br><br><br><br><br>
2. Consider the CBC-mode of encryption with a block cipher having a 256-bit key and 128-bit block length to encrypt a 512-bit
message. The length of the resulting ciphertext in bits is:<br><br>
a) 256<br>
b) 128<br>
c) 640<br>
d) None of these<br><br>
The length of the ciphertext will be 512 bits plus additional 128 bits for the IV , which is 640 bits. <br><br>So the answer is **c**.<br><br><br><br><br>
3. Which of the following is(are) true about Feistel and SPN networks?<br><br>
a. SPRP can be constructed using 4-round Feistel network.<br>
b. Diffusion is used to produce avalanche effect in an SPN.<br>
c. S-boxes are used to produce confusion in an SPN.<br>
d. All the above.<br><br>
The first statement is correct. The second statement is also true. The third statement is false, as S-boxes are publicly known
and hence alone cannot produce confusion. Rather, its key-mixing step, which along with S-boxes, which produce confusion
in SPN. <br><br>So the correct answers are **a** and **b**.<br><br><br><br><br>
4. Given Fk is a secure PRF, define a keyed function F
'
k
, where F
'
k
(x) = Fk(x) if x is even, else F
'
k
(x) = Fk(x + 1). Then
which of the following is(are) false?<br><br>
a) F
'
k
is a secure PRF<br>
b) F
'
k
is a secure PRP<br>
c) F
'
k
is a secure SPRP<br>
d) F
'
k
can be used to instantiate the CTR mode of block cipher<br><br>
The construction F
'
k
is not a secure PRF (and hence it is not PRP/SPRP, due to which it cannot be used in any of the modes
of operation). The reason that F
'
k
is not a PRF is that F
'
k
gives the same output for an even x and the corresponding x − 1,
which can happen only with a negligible probability for a TRF.<br><br>
So the correct answers are **a**, **b**, **c** and **d**.<br><br><br><br><br>
5. Let F : {0, 1}
n × {0, 1}
n → {0, 1}
n be a secure PRF. Then which of the following constructions is/are not necessarily a
secure PRF?<br><br>
a) F
'
: {0, 1}
n × {0, 1}
2n → {0, 1}
n, where F
'
k
(x||y)
def
= Fk(x) ⊕ Fk(y)<br>
b) F
'
: {0, 1}
n × {0, 1}
2n → {0, 1}
n, where F
'
k
(x||y)
def
= Fk(x)||Fk(y)<br>
c) F
'
: {0, 1}
n × {0, 1}
2n → {0, 1}
n, where F
'
k
(x||y)
def
= Fk(x) ∧ Fk(y)
d) F
'
: {0, 1}
n × {0, 1}
n → {0, 1}
2n, where F
'
k
(x)
def
= Fk(x)||Fk(x ⊕ 1
n)<br><br>
None of the constructions is a secure PRF. For the first construction, the value of F
'
k
(x||y) is the same as F
'
k
(y||x), which
happens only with a negligible probability for a TRF. For the second construction, if F
'
k
(x||y)
def
= Fk(x)||Fk(y) = a||b,
then F
'
k
(y||x) = b||a, which happens for a TRF only with a negligible probability. For the third construction, the value of
F
'
k
(x||y) is the same as F
'
k
(y||x), which happens only with a negligible probability for a TRF. For the fourth construction,
the value of F
'
k
(x)is the same as F
'
k
(x ⊕ 1n), which happens only with a negligible probability for a TRF.<br><br>
So the answers are **a**, **b**, **c** and **d**.<br><br><br><br><br>