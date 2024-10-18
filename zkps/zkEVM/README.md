## zk-EVMs

<br>

### tl; dr

<br>

* with zk proofs, zk-rollup can achieve better scalability, security, and faster finality as a scaling solution for ethereum.
* zk-EVMs are a scaling solution compatible with ethereum. other solutions such as zksync lite, loopring, and starknet were not evm-compatible.
* example: the bundling of txs happening within a certain period and settling the proof of a block of txs on the ethereum network instead of the full list of tx that may congest the network.
* *they use **[ZK-SNARK](https://github.com/go-outside-labs/blockchains-protocol-design/blob/main/zero_knowledge_proofs/proofs/zkSNARKS.md)** technology to make cryptographic proofs of execution of Ethereum-like txs, either to make it much easier to verify the Ethereum chain itself or to build ZK-rollups that are (close to) equivalent to what Ethereum provides but are much more scalable.* - vitalik

<br>

---

### design challenges

<br>

* evm has limited support of elliptic curves, hard to do proof recursion since cyclic elliptic curve is not directly supported.
* evm word size is 256bit, and zkp work over prime fields. mismatch field arithmetic inside a circuit requires range proofs, which adds many constraints per evm step (blowing up the the circuit size).
* evm has many special opcodes, bringing challenges to circuit design.
* evm is a stack-based vm. zksync and starkware architectures define their own ir/air in the register-based model (language compatible instead of native evm-compatible).
* ethereum storage layout carries large overhead, relying on keccak and mpt (both not zk-friendly).
* machine-based proof has a large overhead (how to complete an evm circuit?).

<br>


---

### recent advancements

<br>

* usage of polynomial commitment, lifting constraints to any degree with a universal or transparent setup.
* lookup table arguments and customized gadgets, optimizing zk-unfriendly primitives (bitwise operations).
* recursive proof is more feasible. this type of proof has a large overhead as it relies on special pairing-friendly cyclic elliptic curves (mnt). halo can avoid the need for a pairing-friendly curve and amortize the cost of recursion using special inner product argument.
* hardware acceleration, making proving more efficient.


<br>

---

### types

<br>


* type 1, fully ethereum equivalent. example: taiko and the **[community zkevm by pse](https://github.com/privacy-scaling-explorations/zkevm-specs)**.
* type 2, fully evm equivalent: might differ on data structure and state trees. example: scroll and polygon hermez.
* type 2.5, evm-equivalent, except for gas costs (increased).
* type 3, almost evm-equivalent.
* type 4, high-level-language equivalent (compatible with smart contract languages). example: zksync.

<br>

<p align="center">
<img width="450" src="https://user-images.githubusercontent.com/1130416/234139749-4dbac8ab-d742-45f3-b920-b0b51d8698b5.png">
</p>



<br>

---

### in this dir

<br>

* **[zk-rollups overview](rollups.md)**
* **[zkSync](zkSync)**
* **[starkware](starkware.md)**
* **[polygon hermez](polygon.md)**
* **[scroll](scroll.md)**
* **[taiko](taiko.md)**

<br>

----

### external resources

<br>

* **[l2 beat scaling](https://l2beat.com/scaling/tvl)**
* **[scroll blog post on zk-evms](https://scroll.io/blog/zkEVM)**
* **[the different types of zk-evms, by vitalik](https://vitalik.eth.limo/general/2022/08/04/zkevm.html)**
* **[how will ethereum's multi-client philosophy interact with zk-evms, by vitalik](https://vitalik.ca/general/2023/03/31/zkmulticlient.html)**
* **[pse series on zkevms](https://mirror.xyz/privacy-scaling-explorations.eth/I5BzurX-T6slFaPbA4i3hVrO7U2VkBR45eO-N3CSnSg)**

