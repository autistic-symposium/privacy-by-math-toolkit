## ⛓🫱🏻‍🫲🏽 zero-knowledge proofs

<br>

<p align="center">
<img src="https://user-images.githubusercontent.com/1130416/234397705-090a0c7b-5d96-49f8-8eaa-183297e3fe37.png" width="50%" align="center" style="padding:1px;border:1px solid black;"/>

<br>
<br>

### tl; dr

<br>

* **zk-rollups** write transactions to ethereum as calldata, using compression techniques to reduce transaction data.
  * while calldata is not stored as part of the evm's state, it persists on-chain as part of the chain's history logs.
* the zk-rollup’s state, which includes l2 accounts and balances, is represented as a merkle tree.
* users in the zk-rollup sign transactions and submit them to l2 operators for processing and inclusion in the next batch.
    * in some cases, the operator is a centralized entity (the sequencer), that executes transactions, aggregates them into batches, and submits to L1.
* the rollup contract won't automatically accept the proposed state commitment until the operator proves the new merkle root resulted from correct updates to the rollup’s state (this comes from validity proofs).
* **zero-knowledge proofs** represent **programs as circuits**, where a **prover** generates a proof from public and private inputs, and a **verifier** computes the output if the statement is correct (without any information regarding the private input).

<br>

#### three fundamental characteristics define a ZKP:
  * completeness (if a statement is true, then an honest verifier can be convinced by an honest prover that they possess knowledge about the correct input).
  * soundness (if a statement is false, then no dishonest prover can unilaterally convince an honest verifier that they have knowledge about the correct input).
  * zero-knowledge (if the state is true, then the verifier learns nothing more from the prover other than that).

<br>

#### zk proofs use cases:
  * **private transactions**: blockchains such as zcash, with privacy-preserving txs.
  * **verifiable computations**: decentralized oracle networks, providing smart contracts with access to off-chain data.
  * **highly-scalable and secure l2s**: verifiable computations through methods such as zk-rollups, validiums, and volition by they use l1s as a settlement layer.
  * **decentralized identity and authentication**: zkps can underpin identity management systems to enable users to validate their identity.



<br>

---

### in this dir

<br>

* **[zk-EVMs](zkEVM)**
* **[number theory](number_theory)**
* **[proof systems](proofs)**
* **[cryptographic primitives](primitives)**
* **[machine learning](applications/ml.md)**
* **[privacy-enhancing technologies](applications/privacy_enhancing_technologies.md)**
* **[incomplete catalog of zkp projects](applications/zkp_projects.md)**


<br>

----


### more resources

<br>

* **[zkiap](https://zkiap.com/)**
* **[zkrepl](https://zkrepl.dev/)**
* **[zk-learnng](https://zk-learning.org/)**
* **[pse's mirror](https://mirror.xyz/privacy-scaling-explorations.eth)**
* **[0xparc on circom](https://learn.0xparc.org/circom/)**
* **[0xparc on halo2](https://learn.0xparc.org/halo2/)**
* **[zero knowledge postcast youtube](https://www.youtube.com/@zeroknowledgefm)**
* **[rollups are not real, by jon charbonneau](https://joncharbonneau.substack.com/p/rollups-arent-real)**
* **[what are zk proofs, ethereum foundation](https://ethereum.org/en/zero-knowledge-proofs/)**
* **[the zk-ECDSA landscape, by pse (ethereum foundation)](https://mirror.xyz/privacy-scaling-explorations.eth/djxf2g9VzUcss1e-gWIL2DSRD4stWggtTOcgsv1RlxY)**
* **the state of zk applications in ethereum, by andyguzman.eth: [1](https://mirror.xyz/andyguzman.eth/p4nNk7Rr-2i-uZDO_lTHJEWtNv3nYt2N2z3Cwly8RHc) and [2](https://mirror.xyz/andyguzman.eth/ZZRLBlx2KjlNnQ84v1doMKg_8QO-XRjYxFfT1Fm_ZDw)**
* **[zero knowledge dapp from 0 to production, by vivian plasencia](https://vivianblog.hashnode.dev/how-to-create-a-zero-knowledge-dapp-from-zero-to-production)**
* **[an evolution of models for zkps, with sarah meiklejohn](https://youtube.com/watch?v=HO97kVMI3SE&t=2s)**
* **[an incomplete guide to folding](https://taiko.mirror.xyz/tk8LoE-rC2w0MJ4wCWwaJwbq8-Ih8DXnLUf7aJX1FbU)**
* **[a new era: safe deploys on zksync era](https://safe.mirror.xyz/yvnFJxFWrlHTXZFBLfQiKuPyW7zwa2TSurXz5Btl9Jk)**
* **[binius: highly efficient proofs over binary fields](https://vitalik.eth.limo/general/2024/04/29/binius.html)**


