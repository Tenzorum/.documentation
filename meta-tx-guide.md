# Hitch hiker's guide to Meta-txs

## What do meta-txs allow you to do?

Meta txs are transactions that are packaged with other meta details that enables the delegated execution of the transaction without requiring end users to sign transactions with key pairs that have gas. 

What are Meta-Transactions? They are transactions being executed by a third party that covers the gas fees, instead of the user. It means that a wallet, exchange, game or any application can allow people to use their systems without having to own ETH to do anything that touches the Blockchain.

Meta-txs along with a certain layer 2 architecture enables  enable onchain transactions without requiring gas on the key. Thus enabling the concept and existence of 'a gasless transaction'. 

Thus enabling the concept and existence of 'a gasless transaction'. 


### What is exactly is a meta-tx?

Normal tx format


> web3.eth.getTransaction('0xc5eee3ae9cf10fbee05325e3a25c3b19489783612e36cb55b054c2cb4f82fc28')
{
  blockHash: '0xdb85c62ef50103f08e9220b59d6c08cbfb52e61d84926dedb3fe9b6940e6bbea',
  blockNumber: 290081,
  from: '0x1dcb8d1f0fcc8cbc8c2d76528e877f915e299fbe',
  gas: 90000,
  gasPrice: 50000000000',
  hash: '0xc5eee3ae9cf10fbee05325e3a25c3b19489783612e36cb55b054c2cb4f82fc28',
  input: '0x',
  nonce: 34344,
  to: '0x702bd0d370bbf0b97b66fe95578c62697c583393',
  transactionIndex: 0,
  value: 5000111390000000000'
}

##### Added Meta tx fields

Data: The contents of the letter is more complex. It is encoded information detailing a list of actions to take including a hash of the name of the function to call along with arguments to pass to that function.

Reward: Economics are important to incentivize a decentralized system. If you want ‘desktop miners’ to pay the gas to submit your transaction, you’ll need to pay up. These funds will not come from your account. They will come out of the identity proxy smart contract. Ether or tokens can be used to pay miners.

Requirements: There can be extended requirements that are checked within the smart contract too. One example is a chronological check. Let’s say the transaction can only go through at the end of the month. The contract can verify this.

## How do the execution of meta-txs work?

->

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

https://twitter.com/owocki/status/1021859962882908160
https://twitter.com/MarkBeylin/status/1022267133818941441
https://twitter.com/lyricalpolymath/status/1042841114762465285
https://twitter.com/owocki/status/1043276458930593794
