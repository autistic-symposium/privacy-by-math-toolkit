## zk-STARKS

<br>

### tl; dr

<br>

* the T stands for "transparent", resolving one of the primary weakness of zk-snarks, its reliance on a trusted setup (they can work without the trusted setup of common reference string (crs)). instead, they rely on publicly verifiable randomness to setup parameters for generating and verifying proofs.
* thye also come with much simpler cryptographic assumptions, avoiding the need for elliptic curves, pairings, and knowledge of expoent assumptions - instead relying on hashes and information theory (secure on the quantum standard).
* the size of a proof goes up from 288 bytes to a few hundred kilobytes (making it more expensive to verify on ethereum).
* it provides more scalability because the time needed to prove and verify validity proofs increases quasilinearly in relation to the complexity of the underlying computation.

<br>

---

### resources

<br>

* [risc0, zk platform based on zk-starks and risc-v microarchtecture](https://github.com/risc0/risc0)
* [starks, part I: proof with polynomials, by vitalik](https://vitalik.ca/general/2017/11/09/starks_part_1.html)
* [starks, part II: thank you goodness it's fri-day, by vitalik ](https://vitalik.ca/general/2017/11/22/starks_part_2.html)
* [starks, part III: into the weeds, by vitalik](https://vitalik.ca/general/2018/07/21/starks_part_3.html)
* [stark 101 videos, by starkware](https://www.youtube.com/watch?v=iuNbrTkH2ik)
