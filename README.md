# EigenMPCGuard

Threshold Cryptography for Secure Multi-Party Computation on EigenLayer

This project is focused on TEE-based AVS on EigenLayer by enabling secure multi-party computation (MPC) through threshold cryptography. MPC allows multiple parties to jointly compute a function over their private inputs without revealing the inputs to each other. This has a wide range of applications, from privacy-preserving data analytics to secure auctions and voting.

The core idea behind threshold cryptography is that a secret key is split among n parties, where at least k of them must cooperate to perform cryptographic operations like decryption or signing. This provides strong security guarantees - even if up to (n-k) parties are compromised, the secret key remains safe.

By leveraging EigenLayer's decentralized network of TEE committees, we can build a threshold cryptography AVS that enables robust, privacy-preserving MPC. Here's how it would work:

**Key Generation and Distribution**
* The MPC application would generate a secret key and split it among the TEE committee members using a threshold scheme.
* Each committee member's share of the key would be securely stored in their TEE, ensuring that no single party can access the full key.

**Computation**
* Parties with private inputs would send their data to the MPC AVS, which would distribute the computation across the TEE committee.
* Each committee member would perform a partial computation on the encrypted data using their key share, without ever seeing the raw inputs.
* The partially computed results would be aggregated, and the final output would be returned to the parties, preserving the privacy of the inputs.

**Security and Reliability**
* The decentralized TEE committee ensures that the MPC computation is secure even if some committee members are compromised, as long as the threshold number of members remain honest.
* The economic incentives and slashing mechanisms of EigenLayer provide an additional layer of security, as committee members have a financial stake in maintaining the integrity of the system.

This threshold cryptography AVS would enable a wide range of privacy-preserving applications, from secure data analytics and machine learning to confidential auctions and voting systems. By leveraging the unique properties of EigenLayer's TEE committees, it can provide a level of security and reliability that is difficult to achieve with other MPC approaches.

## Proof of Concept

As a proof of concept, we have build a secure multi-party auction system using the threshold cryptography AVS. In this system, bidders would submit their bids encrypted using the public key of the MPC AVS. The TEE committee would then perform the auction clearing computation without ever seeing the raw bid values, and return the auction result to the participants.

To demonstrate the feasibility of this approach, we are implementing a prototype using open-source threshold cryptography libraries like JIFF or MP-SPDZ, and integrate it with the EigenLayer TEE committee infrastructure. The key technical challenges would be ensuring the secure generation and distribution of the threshold key, as well as the efficient aggregation of the partially computed results.

By open-sourcing the core components of this proof of concept, we are contributing to the broader ecosystem of secure multi-party computation tools and encourage further innovation in this space.

