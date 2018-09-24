# TSNN (Tenzorum Service Node Network) - *in progress & incomplete*

The TSNN is an offchain p2p service node network that recieves offchain meta-transactions (transactions with more data attached) and executes them on behalf of users (the responsibility of executing the transaction is 'delegated to the service node network').

These delegated transactions are called meta-transactions as they carry additional data fields along side the usual signed ethereum message. These meta-fields are used to communicate with the service node and enable the delegated execution of the transaction.

This is designed to enable the possibility of onchain transactions using a private key that holds no gas. Onchain interactions require gas and this is created as a work around with the responsibilities of paying for gas to be delegated to a contract. The contract will require an indication of permissioning to a chain of public keys with execution access. (think 725 identity key management)

Summary: Onchain transactions with gas paid for by either the user or a third party.

## Protocol for executing a meta-transaction

![](https://i.imgur.com/tY0PHGi.png)

// Diagram: need to depict staking and service node onchain execution of meta-tx

1. User uses private key to prepare a meta-tx with a reward for its execution

2. Meta-tx is relayed to the service node

3. Service node recieves the meta-tx and validates it. Checks if the associated contract address is associated with the matching public key given with valid delegation permissions to execute the meta-tx + then checks if other fields of the meta-tx is valid.

4. Meta-tx are propagated around the network and executed.

5. Once service nodes carry out onchain transaction, they claim the reward encoded into the meta-tx

6. Service node pk with gas executes the bytecode for the meta-tx

### Repositories

https://github.com/Tenzorum/tenz-client-sdk
https://github.com/Tenzorum/tenz-tsnn
https://github.com/Tenzorum/tenz-tsn-js

### Jargon & definition of terms

Meta-tx (Meta transaction): Tx with additional meta data fields eg. reward details

Relay: Act of sending meta-tx away to offchain 2nd layer / service node

Relayer: The user / dapp that is sending the tx away to the 2nd layer / service node

Delegation: Passing on reponsibility of executing the tx

Delegated-tx (Delegated transaction): Meta-tx that has been relayered

Service node: Server that recieves meta-txs and confirms the validity of the tx.

Tx-pool: Pending layer of meta-txs that are ready to be executed

Gasless transaction - users point of view

### Architectural requirements, challenges, issues, decisions to be made

- Meta-transactions with fields
- Offchain server for meta-transactions to be sent to
- Onchain contract with onchain public keychain association / permissioning registry
- Smart contract identity key management and permissioning establishes the relationship between the funds held in the multi-sign/identity wallet with the public key. Checking to see if the public key is given permission to sign transactions of intent and execute delegated transactions. Standard that creates / indicated permissioned delegate access between pbulic key with nothing on it and contract with funds on it + other configurations that will come later -> included as part of ipas. https://github.com/Tenzorum/personal-wallet-contracts Tenzorum's Smart Contract builds around personal multisignature wallets and key recovery are building at the core a gasless transaction protocol. 
- we do signing on client signing using tenzorum's client side signing utility, package avail tenzorum-pkg, forked from partiy signer.We want clients to sign the data. Tamperproof? Safer to transact over internet, less tamperable - saving private key on client side. 

- Need to decide on p2p protocol for inter-client node communications

- algorithm to determine meta-tx distribution load, source of randomness, weighted by what is staked?

## Meta-transaction format

The TSNN meta-tx RPC call will be formatted in following way and how a project would prepare meta-transactions.

**Formatt**
```
{
      uint8 _v, bytes32 _r, bytes32 _s,
      address _from, //the subscriber
      address _to, //the publisher
      uint _value, //wei value of transfer
      bytes _data, //data input
      address _rewardType, //reward relayers in tokens or ETH
      uint _rewardAmount //amount to reward
}
```

**Rx**

```
    ##Client SDK

    HTTP POST https://login.tenzorum.app/execute + {payload}
    GRAPHQL endpoint mutation ExecuteGaslessTx($from: $WalletAddress!, $to: $WalletAddress!, $amount: Int!) {
                       executeTransaction(from: $from, to: $to) {
                            amount
                       }
                     }

    ##Relay RPG
    - Coming
```

**Tx**
```
{
    function execute(
      uint8 _v, bytes32 _r, bytes32 _s,
      address _from,
      address _to,
      uint _value,
      bytes _data,
      address _rewardType, uint _rewardAmount) public
}
```

### Notes & comments

- This implementation requires signing of the transaction on the client side (v, r, s).
- The public addres (from) is received from the user's client-side private key. 
- These private keys will be permissioned keys with controlled access to a user's personal multisig wallet. 
- The (to) public address will be the receiver's address who can receive transactions from any ERC-20 token or Ether. 
- The (value) will be sent in wei from the client side, however we are definitely exploring further abstractions. and how to implement in terms of UI
- The (data) input is there for further data standard implementations. + ERC191 like data standard or other possibilities for even fields like who is covering the cost of gas, or the dapp being used etc.
- The (rewardType) is a selection of whether we want to reward the service node relayers with a known token or Ether. 
- The (rewardAmount) will be an amount to send to further incentivise service node relayers to relay your transaction. 

# Service node staking and economics

Coming soon...

# Service node pool economics

Coming soon...

## Repositories

**TSNN (Tenzorum Service Node Network)**

[Tenzorum Service Node (TSNN)](https://github.com/Tenzorum/TSNN-Service-Node) - service node client

[Service Node Network Interface and Tx selection](https://github.com/Tenzorum/TSNN-network-interface) - network interface & tx propagation

[TSNN SDK](https://github.com/Tenzorum/TSNN-client-sdk) - relaying txs to TSNN

[Meta-Tx TSNN standard](https://github.com/Tenzorum/meta-transaction-format-share)

## Scenarios

1. User's own funds are used to cover gas...

2. Dapp uses their own funds to cover gas...


## Focus on interloperability

+ https://github.com/Tenzorum/personal-wallet-contracts
+ https://github.com/austintgriffith/meta-transaction-format-share

## Relevant links

https://github.com/planet-ethereum/relay-network
https://github.com/ethberlin-hackathon/ETHBerlin-Teambuilding/issues/35 (edited)
https://github.com/EthWorks/EthereumIdentitySDK
https://github.com/jpitts/eth-community-discussions/blob/master/meta-transactions.md (edited)
https://github.com/austintgriffith/meta-transaction-format-share
https://docs.google.com/presentation/d/17dsIV0wUYRK7OlCD87C9Snq8lI3WtDLWCP4W7hCZWyI/edit#slide=id.g3d77437fd3_0_0
https://medium.com/@austin_48503/ethereum-meta-transactions-90ccf0859e84
