## Implementions & projects working on meta-txs

We have a community thing: https://github.com/austintgriffith/meta-transaction-format-share

#### Tenzorum

https://github.com/Tenzorum/.documentation/blob/master/TSNN.md

#### Metatx
- [Bouncer Proxy](https://github.com/austintgriffith/bouncer-proxy) - GitHub Project
- [Delegated Execution Subscriptions](https://github.com/austintgriffith/delegated-execution-subscriptions) - combines Bouncer Proxy w/ Token Subscriptions
- [Meta transactions on Ethereum via Identity Proxy Contract](https://www.youtube.com/watch?v=6r3SqCcEVU4&feature=youtu.be) - youtube video


#### uPort
- [Making uPort Smart Contracts Smarter, Part 3: Fixing UX with Meta Txns](https://medium.com/uport/making-uport-smart-contracts-smarter-part-3-fixing-user-experience-with-meta-transactions-105209ed43e0) - Medium article
- [Meta Transaction Relaying Server](https://developer.uport.me/rest-apis/relay-server/)

Sandbox for experimenting with etherless meta transactions. The heart of the trick is to sign and recover transactions using Ethereum key pairs both on and off chain.

#### Planet Ethereum

[Gas relay execution market](https://github.com/planet-ethereum/relay-network)

#### Status

[Status Gas Relays](https://docs.google.com/presentation/d/17dsIV0wUYRK7OlCD87C9Snq8lI3WtDLWCP4W7hCZWyI/edit#slide=id.g3d77437fd3_0_0)

#### Limechain

https://github.com/LimeChain/IdentityProxy

#### Hermes Network

https://github.com/ethberlin-hackathon/ETHBerlin-Teambuilding/issues/35

#### EthereumIdentitySDK

https://github.com/EthWorks/EthereumIdentitySDK

### Discussions

https://github.com/ethereum/EIPs/issues/965

## **Meta-tx user experience use cases**

How meta-txs can be used...

### `Web3 onboarding`

#### Avsa / Executable Signed Transactions
- [The magic of executable signed messages to login and do actions](https://ethereum-magicians.org/t/erc-1077-and-erc-1078-the-magic-of-executable-signed-messages-to-login-and-do-actions/351) - post to the Magicians' Forum by [alexvandesande](https://github.com/alexvandesande)
- [ERC-1077](https://github.com/ethereum/EIPs/pull/1077) - Executable Signed Messages refunded by the contract
- [ERC-1078](https://github.com/ethereum/EIPs/pull/1078) - Log in / signup using ENS subdomains
- [Universal Logins for Ethereum - UX Unconf Toronto 2018](https://www.youtube.com/watch?v=qF2lhJzngto&feature=youtu.be) - youtube video

Allowing users to sign messages to show intent of execution, but allowing a third party relayer to execute them is an emerging pattern being used in many projects. 


https://medium.com/@lyricalpolymath/all-aboard-alliance-for-mass-adoption-of-the-blockchain-209bde271778


#### HatchCrypto unilogin
- [unilogin](https://github.com/HatchCrypto/unilogin) - GitHub project

This is a React - Web3 - Solidity Proof of Concept signup / login design pattern with a minimal Ethereum native scheme that doesn't require passwords, backing up private keys nor typing seed phrases. It also allows for a user to sign messages to show intent of execution along similar guidelines.


- [All aboard alliance for mass adoption](https://medium.com/@lyricalpolymath/all-aboard-alliance-for-mass-adoption-of-the-blockchain-209bde271778)
- [ERC1077 Universal logins user onboarding flow](https://www.youtube.com/watch?v=qF2lhJzngto)
- [**Ethereum Meta Transactions** - Lowering barriers to drive mass Ethereum adoption](https://medium.com/@austin_48503/ethereum-meta-transactions-90ccf0859e84
)

### `Wallets`

- Gnosis Safe - [Website](https://safe.gnosis.io/) - [Gnosis Safe contracts](https://github.com/gnosis/safe-contracts) Aims to provide all users with a convenient, yet secure way to manage their funds and interact with decentralized applications on Ethereum.

Aims to provide all users with a convenient, yet secure way to manage their funds and interact with decentralized applications on Ethereum.


### `Token subscriptions`

https://medium.com/gitcoin/technical-deep-dive-architecture-choices-for-subscriptions-on-the-blockchain-erc948-

[Ethereum Grants - Recurring token subscriptions powered by meta transactions](https://www.youtube.com/watch?v=Dgc_siqNrOA)

### `Gasless product model`

- https://twitter.com/owocki/status/1021859962882908160
- https://twitter.com/MarkBeylin/status/1022267133818941441
- https://twitter.com/lyricalpolymath/status/1042841114762465285
- https://twitter.com/owocki/status/1043276458930593794
