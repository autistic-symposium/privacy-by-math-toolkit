## kate polynomial commitment scheme (pronounced kah-tay)

<br>

### tl; dr

<br>

* it allows a prover to compute a commitment to a polynomial, with the properties that this commitment can later be opened at any position.
* the prover shows that the value of the polynomial at a certan position is equal to a claimed value.
* once a **commitment** (an elliptic curve point) is sent to the verifier, the prover cannot change the polynomial they are working with.
* a merkle tree is a "vector commitment": using a merkle tree of depth, you can compute a commitment to a list of elements of fixed length. using merkle proofs, you can provide a proof that an element is a member of this vector at position using hashes.
* in the kate commitment scheme, the element is the commitment to the polynomial: could the prover (without knowing) find another polynomial that has the same commitment.x

<br>

<img width="586" src="https://user-images.githubusercontent.com/1130416/234472661-000ccabb-2bce-4e16-8a51-f599c04b643d.png">


<br>

----

### resources

<br>

* **[the original kate paper](https://www.iacr.org/archive/asiacrypt2010/6477178/6477178.pdf)**
* **[kzg polynomial commitments, by dankrad feist](https://dankradfeist.de/ethereum/2020/06/16/kate-polynomial-commitments.html)**
* **[the kzg ceremony, by carl beekhuizen](https://archive.devcon.org/archive/watch/6/the-kzg-ceremony-or-how-i-learnt-to-stop-worrying-and-love-trusted-setups/?tab=YouTube)**
