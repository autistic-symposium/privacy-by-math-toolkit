## cryptographic primitives

<br>

### bls signatures

* used in the beacon chain to verify large numbers of signtures.
* invented by dan boneh, ben lynn, and hovav shacham.
* in optimistic rollups such as arbitrum and optimism, each tx must be accompanied by its own signature. these signatures are stored on l1 calldata, a read-only format that's commited as a part of a transaction rather than to (expensive) contract storage.
* storing txs and signatures as calldata is the cheapst method available for rollups to keep data on l1.
* the key property of bls signatures is that multiple signatures can be combined into one - so only one aggregate signature needs to be verified and stored on-chain (meaning less gas fees).

<br>

![](https://user-images.githubusercontent.com/1130416/235320176-855998db-d998-45b3-a9cf-e160c4825993.png)


<br>

----

### shamir's secret sharing

<br>

* secret sharing algorithm to distribute private information among a group, and the secret cannot be revealed unless a quorum of the groups acts together to pool their knowledge.
* the secret is matematically divided into parts. if an attacker steals some shares, it's impossible for the attacker to reconstrcut the secret unless they have stolen a quorum number of shares.
* uses cases: password managers, encrypted emails, and crypto wallets.

<br>

![](https://user-images.githubusercontent.com/1130416/235320099-6ab37a6b-14df-40d4-9c9c-b8142bb6a30b.png)


<br>

----

### resources

<br>

