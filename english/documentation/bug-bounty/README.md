# Bug Bounty

A bug bounty program for Liquity’s smart contracts is now live. We intend for hackers to look for smart contract vulnerabilities in our system that can lead to loss of funds or locked components.

The preferred way to submit a vulnerability is through **Liquity's Vault** on the [Hats Finance platform. ](https://app.hats.finance/vaults)If for any reason, Hats can't be used, vulnerabilities can also be sent using the method described below.

### Rewards

Vulnerability reports will be scored using the [CVSS v3](https://www.first.org/cvss/) standard. The reward amounts for different types of vulnerabilities are:

**🚨 Critical (CVSS 9.0–10.0)**

→ $125,000 - $250,000

**⚠️ Major (CVSS 7.0–8.9)**

→ $25,000 - $125,000​

**⚡ Medium (CVSS 4.0–6.9)**

→ $2,500 - $25,000

**🐛 Low (CVSS 1.0–3.9)**

→ $500 - $2,500

Rewards will be awarded at the sole discretion of Liquity AG. The quality of the report and reproduction instructions can impact the reward. Rewards are denominated and paid out in USD. If both parties agree, rewards can also be paid out in crypto.

For this initial bug bounty program, there is a **maximum bounty pool of $250,000**.

The bug bounty program is ongoing and has been running since February 19th, 2021.

### Reporting a Vulnerability

Please responsibly disclose any findings to the development team, following these instructions:

* In order to report a vulnerability, please write an email to **security@liquity.org** with \[SECURITY DISCLOSURE] in the subject of the email.
* For sensitive vulnerabilities, please the encrypt the email using this [PGP key](https://keys.mailvelope.com/pks/lookup?op=get\&search=security@liquity.org) (Fingerprint: D4BA B0E7 3B99 4FC5 79DC 9E0A C640 0C72 C5B8 CA28).
* We will make our best effort to reply in a timely manner and provide a timeline for resolution.
* Please include a detailed report on the vulnerability with _clear_ reproduction steps. The quality of the report can impact the reward amount.

Failure to do so will result in a finding being ineligible for any bounties.

### Scope

In scope for the bug bounty are all the smart contract components of the Liquity protocol. They can be found in the following repositories:

* [https://github.com/liquity/dev](https://github.com/liquity/dev)

Solidity code under the `contracts` directory:

* Excluding `contracts/Dependencies`
* Excluding `contracts/LPRewards/Dependencies`

### Out of scope

* Any frontend applications or client-side code, except where the frontend explicitly calls a smart contract function.
* Mismatch of the functionality of the contracts and outdated spec documents.
* Issues with use of Tellor as a secondary fallback (see [this security advisory](https://github.com/liquity/dev/security/advisories/GHSA-5x6p-646h-mmgj) for more context).

### Areas of interest

These are some examples of vulnerabilities that would be interesting:&#x20;

* Stealing tokens or manipulating the token generation process.
* Locking or freezing any of the Liquity contracts.
* Griefing attacks: is it possible to block liquidations, redemptions, borrower operations, rewards distributions, etc?
* Do the desired constraints on borrower operations hold?
* Flash loan exploits
* LQTY token exploits involving the LockupContracts
* Frontend initiated smart contract interactions which unexpectedly impact the user negatively - e.g. MEV risk from withdrawing liquidity from an AMM

### Resources

* [Liquity README](https://github.com/liquity/beta/blob/main/README.md)

### Eligibility

Terms for eligible bounties:&#x20;

* Only unknown vulnerabilities will be awarded a bounty; in case of duplicate reports, the first report will be awarded the bounty.
* Public disclosure of the vulnerability, before explicit consent from Liquity AG to do so, will make the vulnerability ineligible for a bounty.
* Attempting to exploit the vulnerability in a public Ethereum network will also make it ineligible for a bounty.&#x20;
