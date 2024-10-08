## zk proofs applied to ml (zkml)

<br>


### tl; dr


<br>

<img width="600"  src="https://user-images.githubusercontent.com/1130416/234938321-a0b052b6-e754-4e80-8351-0daa847ebd12.png">


<br>

----

### challenges

<br>

* transpile NNs into ZKP circuts (floating-point weigths -> fixed-point arithmetic)
* model size/depth

<br>

---

<br>

### ideas

* model authenticity
  - assurance that the ml model is the one that run (e.g. the most accurate one)
  - functional commitments allow the prover to establosj that it used a commited model (but no guarantess about the commited model).
* model integrity
  - assurance that the same ml algorithm is ran on different data the same way
* attestations  
  - integrate attestations from external parties
 * decentralized inference or traning
  - perform ml training in a decentralized way 
 * proof of personhood
 
 <br>
 
 ---
 
 ### resources
 
 <br>
 
 * **[humanness in the age of ai, by worldcoin](https://worldcoin.org/blog/engineering/humanness-in-the-age-of-ai)**
 * **[zk-img: attested images via zk-proofs, d. kang et al](https://arxiv.org/pdf/2211.04775.pdf)**
 * **[checks and balances ml and zk, by a16](https://a16zcrypto.com/content/article/checks-and-balances-machine-learning-and-zero-knowledge-proofs/)**
 * **[trustless verification of ml, by d. kang](https://ddkang.github.io/blog/2022/10/18/trustless/)**
 * **[tachikoma, neural nets for zk proof systems](https://github.com/zk-ml/tachikoma)**
 * **[zkml, framework for constructing proofs of ml model in zksnarks](https://github.com/ddkang/zkml)**
 * **[ezkl, deep learning inference in zk-snark](https://github.com/zkonduit/ezkl)**
 * **[unraveling zkml, by dr. cathie so](https://www.canva.com/design/DAFgqqAboU0/4HscC5E3YkFRFk3bB64chw/view#1)**
