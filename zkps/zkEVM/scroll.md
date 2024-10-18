## scroll

<br>

### tl; dr

<br>

* scroll is an evm-equivalent zk-rollup to scale ethereum. 
* the core piece is the zkevm, used to prove correctness of evm execution in layer 2.
* architecture:
  * scroll node: constructs l2 blocks from user txs, commit them to the ethereum base layer, and passes messgaes between l1 and l2.
  * roller network: generates the zkevm validity proofs to prove that txs are executed correctly.
  * rollup and bridge contracts: provides da for scroll txs, verifies zkevm validity proofs, and allows users to move assets between ethereum and scroll. 

<br>

<img width="600" src="https://user-images.githubusercontent.com/1130416/234146949-a523a484-9b24-43aa-93ac-9817ccf6e51d.png">

<br>

* the rollers serve as provers in the network, responsible for generating validity for the rollup.
  * rollers utilize accelerators such as gpus, fpgas, asics
  * a roller first converts the execution trace from the coordinator to circuit witnesses
  * then generates proofs for each of the zkevm circuits
  * finally, it uses proof aggregation to combine proofs from multiple zkevm circuits into a single block proof.


<br>

<img width="600"  src="https://user-images.githubusercontent.com/1130416/234150191-a8e9296b-ae52-4f3a-a3d3-b933418ec10d.png">

<br>

* workflow of scroll's rollup:

<br>

<img width="610" src="https://user-images.githubusercontent.com/1130416/234150359-d612ac1e-e338-45fa-ab8d-f51fd653b6cd.png">


<br>

---

### resources

<br>

* [scroll on mirror](https://scroll.mirror.xyz/)
