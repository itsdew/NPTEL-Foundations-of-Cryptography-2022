# Solutions for Assignment 3<br><br>
1. Select the incorrect option(s) from the following:<br><br>
a) Stream ciphers are deterministic<br>
b) Stream ciphers are randomized<br>
c) Same key can be used for encrypting multiple messages in stream ciphers<br>
d) Stream ciphers are single-message CPA-secure<br><br>
Stream ciphers have deterministic encryption algorithm, due to which a single key can be used for encrypting a single
message. Consequently, they can never be CPA-secure. <br><br>So the answers are **b**, **c** and **d**.<br><br><br><br><br>
2. Which of the following is/are false for One-Way Functions (OWF)?<br><br>
a) They are randomized functions<br>
b) They are difficult to invert for all elements from the co-domain<br>
c) They are always one-to-one function<br>
d) They are deterministic functions<br><br>
OWF are deterministic functions and they can be many-to-one. Moreover, they are difficult to invert for most of values from
the co-domain, except for a negligible fraction of the co-domain. <br><br>So the answers are **a**, **b** and **c**.<br><br><br><br><br>
3. Which of the following candidates is(are) not necessarily secure PRF(s)? In all the following options, Fs(x) is a secure PRF,
where x, s ∈ {0, 1}
n and the output is also an n-bit string.<br><br>
a) Gs(x) = Fs(x) ⊕ Fs(¯x)<br>
b) Gs(x) = 1||Fs(x), where || denotes the concatenation operation<br>
c) Gs(x) = FFs(x)(x)<br><br>
The first two candidates are not PRFs. For Gs(x)
def
= Fs(x) ⊕ Fs(¯x), the outputs Gs(x) and Gs(¯x) will be the same, which
can happen for a TRF only with a negligible probability. For Gs(x)
def = 1||Fs(x), the output always starts with 1, which can
happen for a TRF only with probability 1/2. The third construction is a secure PRF, as Fs(x) is a pseudo-random output and
hence when F is invoked with a pseudo-random key instead of a random key, the output will be still indistinguishable from
a TRF. <br><br>So the answers are **a** and **b**.<br><br><br><br><br>
4. Let G : {0, 1}
n → {0, 1}l be a secure PRG. We construct a keyed function Fk : {0, 1}
l → {0, 1}
l
, where Fk(x)
def
=
G(k) ⊕ x and use Fk to design an encryption algorithm Enck, for encrypting messages of length l bits. To encrypt a
message m ∈ {0, 1}
l
, algorithm Enck(m) picks a uniformly random r ∈ {0, 1}
l
and outputs the ciphertext (r, Fk(r) ⊕ m).<br><br>
a) Algorithm Enck is single-message COA-secure<br>
b) Algorithm Enck is single-message CPA-secure<br>
c) Algorithm Enck is single-message CCA-secure<br>
d) None of these<br>
The second component of the ciphertext (r, Fk(r)⊕m) is actually G(k)⊕r ⊕m. Since, r is available as the first component
of the ciphertext, the actual ciphertext is G(k) ⊕ m, which is the same as stream cipher. And stream ciphers are only
single-message COA-secure. <br><br>So the answer is **a**.<br><br><br><br><br>
5. Let Π = (Gen, Enc, Dec) be a symmetric-key cipher. Then consider a variant Π' = (Gen, Enc'
, Dec'
) of Π, where
Enc0
k
(m) = Enck(reverse(m)). The steps of Dec'
are performed accordingly. Here reverse(m) denotes the bit string
obtained by reversing the order of the bits of m.
<br><br>
a) If Π is single-message COA-secure, then Π'
is also single-message COA-secure<br>
b) If Π is multi-message COA-secure, then Π'
is also multi-message COA-secure<br>
c) If Π is CPA-secure, then Π'
is also single-message CPA-secure<br>
d) None of these<br><br>
Intuitively, whatever is the security offered by Π, the same security will be offered by Π'
, as reverse(m) also constitutes a
valid message from the message space. <br><br>So the answers are **a**, **b** and **c**.<br><br><br><br><br>
