## PLONK

<br>

### tl; dr

<br>

* **[introduced in 2019](https://eprint.iacr.org/2019/953.pdf)**, plonk stands for **"permutations over lagrange-bases for oecumenical noninteractive arguments of knowledge"**, brining enhancements to the usability of zkps by giving a **universal fully-succinct zk-SNARK with significantly improved
prover run time compared to fully-succinct Sonic**.
* while plonk still requires a trusted setup procedure similar to snarks, but it's **universal and updateable trusted setup**, meaning:
    - instead of there being one separate trusted setup for every program to be proved, there is one single trusted setup for the whole scheme.
    - there is a way for multiple parties to participate in the trsuted setup such that it's secure as long as any one of them is honest, and this multi-party procedure is fully sequential (polynomial commitment, in this case, kate).
* there are two types of constraints:
    - gate constraints (equations between wires attached to the same gate, e.g., a1 * b1 = c1).
    - copy constraints (claims about equality of different wires anywhere in the circuit, e.g., ao = a1)
* **polynomial commitments** is a short object that represents a polynomial, allowing evaluations verification without needing all the data in the polynomial. ** if someone gives you a commitment representing `c` they can give you a proof that can convince you, for some specific `z`, what the value of `P(z)`**.
* a commitment to a degree-d polynomial is made by multiplying each of the first d+1 points in the proving key by the corresponding coefficient in the polynomial, and adding the results together, providing an evaluation of that polynomial at `s` without knowing `s`.



<br>

<img width="593" src="https://user-images.githubusercontent.com/1130416/234398674-d7af7145-e9c8-4dc6-b13a-003745765600.png">



<br>

----

### resources

<br>

* **[understanding plonk, by vitalik](https://vitalik.ca/general/2019/09/22/plonk.html)**
* **[plonk original paper, by ariel gabizon et al](https://eprint.iacr.org/2019/953.pdf)**
* **[plookup original paper, by ariel gabizon et al](https://eprint.iacr.org/2020/315)**
