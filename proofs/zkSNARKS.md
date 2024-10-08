## zk-SNARKS

<br>

### tl; dr

<br>

* introduced in 2011, **zk-snarks stands for "zero-knowledge succint non-interactive argument of knowledge"**, and refers to a proof construction where one can prove possession of certain information, without revealing the information nor any interaction between the prover and verifier. it made it possible to efficiently scale the nuber of polynomials that can be gated, improving speed and potential complex applications.
* a **"succinct" proof is one where both the size of the proof and the time required to verify it grow much more slowly than the computation to be verified**". succint zk proofs can be verified within a few milliseconds**, with a **proof length of only a few hundred bytes** even for large statements.
* this entails enconding the computation into polynomials. **a polynomial commitment** is way to hash a polynomial, and the equations between polynomials can be checked by checking equations between hashes.
* **zcash was the first widespread application of zk-snarks** by encoding some of the network’s consensus rules into it. in may '22, zcash introduced the orchard shielded payment protocol, which utilizes the halo 2 zk proving system (and replace trusted ceremonies).

<br>

#### implementation

* **encoding a polynomial problem**: the program that is to be checked is compiled into a quadractic equation of polynomials, where the equality holds if and only if the program is computed correctly - the prover wants to convince the verifier that this equality holds.
* **succinctness by random sampling**: the verifier chooses a secret evaluation point to reduce the problem from multiplying polynomials and verifying polynomial function equality to simple multiplication and equality check on numbers. - this reduces both the proof size and the verification time.
* **homomorphic enconding/encryption**: an encoding/encryption function E is used that has some homomorphic properties (two operations are homomorphic if you can exchange their order without affecting the resul).
* **zero-knowledge**; verifier can check correct structure without knowing the actual encoded values.




<br>

#### building circuits

1. the first step in turning a tx validity function into a mathematical representation is to break down the logical steps into the smallest possible operations, creating an "arithmetic circuit". this is similar to a boolean circuit where a program is compiled down to discrete AND, OR, NOT.
2. next is to build a **rank 1 constraint system (r1cs)**, to check the values. it's only needed to check that 2 polynomials match at one randoly chosen point in order to verify the proof with high probability. with zk-snarks, techniques such as **homomorphic encryption** and **pairings of elliptic curves** are used to evaluate polynomials blindly.
3. the zero-knowledge part comes from having the prover using "random shifts" of the original polynomials that still satisfy the identity.

<br>

#### zk-snarks applied to create a shielded tx (zcash)

* the sender of a shielded tx constructs a proof to show that, with high probability:
   1. the input values sum to the output values for each shielded transfer.
   2. the sender proves that they have the private spending keys of the input notes, giving them the authority to spend.
   3. the private spending keys of the input notes are linked to a signature over the whole tx, in such a way that the tx cannot be modified by a party that doesn't not have the priv keys.

<br>

---

### resources

<br>


* **[what are zk-snarks, by z-cash](https://z.cash/technology/zksnarks/)**
* **[libsnark, C++ lib for zkSNARKS](https://github.com/scipr-lab/libsnark)**
* **[zk-snarks in a nutshell, by ef](https://blog.ethereum.org/2016/12/05/zksnarks-in-a-nutshell)**
* **[bellman, a crate for building zk-SNARK circuits](https://github.com/zkcrypto/bellman)**
* **[an approximate introduction to how zk-snarks are possible, by vitalik](https://vitalik.ca/general/2021/01/26/snarks.html)**
* **[the crazy security behind the birth of zcash](https://spectrum.ieee.org/the-crazy-security-behind-the-birth-of-zcash)**


<br>

##### halo2

* **[intro to PLONKish/halo2, by ying tong](https://docs.google.com/presentation/d/1UpMo2Ze5iwzpwICPoKkeT04-xGFRp7ZzVPhgnidr-vs/edit#slide=id.g133c45f1bcd_3_36)**
