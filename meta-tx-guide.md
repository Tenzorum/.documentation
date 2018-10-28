# Welcome to meta-txs!

### This page here will look to explain the following things:

* What are meta-txs...
* Why you should be excited about them...

***


### What are meta-txs and how do they work?

// This is a rough high level explaination, the implementation details aren't mentioned here.

Meta-txs stand for meta transactions. They are transactions which are signed by the user but not called by the user. Instead the transaction is sent to a server that executes the transaction for the user. This is known as the meta-tx relay. The server that receives meta-txs and executes them on behalf of the user is known as the relay server that provides the relay service. There are different models of how users gain access to execute meta-txs. 

![](https://i.imgur.com/vZ50sNH.png)

### What do meta-txs solve?

Meta-transactions enable users to authenticate to a server with a key pair which allows them to conduct onchain transactions without any gas in the key pair account.

**Web3 User onboarding:** Since meta-txs abstract out the need for gas on the key to execute onchain, meta-txs enable applications to give 'free' transactions to users without any further user friction. Eg. For your first 5 transactions, your transactions are free. Usually, users who are completely new to web3 products and cryptocurrencies in general will not have any gas and/or other cryptocurrencies. They are often forced to go through the metamask -> KYC exchange process. While this process is inevitable to some extend, meta-txs enable further user engagement through potentially 'free' transactions, thus providing a greater ability for applications to activate their users.

**Wallet key management:** Since meta-txs abstract out the need for gas on the key to execute onchain, they can actually also conduct meta-txs while paying for their own gas usage with their own identity contract wallet. Since users are able to generate keys on different devices and add them to their central identity contract wallet to gain access to execute meta-txs, users no longer require the exportation of their private keys through seed phrases and the behaviour of sending funds from one account to another. They will be able to access their funds from any keys that is authenticated to conduct meta-txs from their identity contract wallet.

**Other miscellaneous usecases:** Scheduled meta-txs which are conditionally executed based on time, token subscriptions ...

An example vision of what could be enabled by meta-txs can shown here: [All-Aboard! Alliance for Mass Adoption of the Blockchain](https://medium.com/@lyricalpolymath/all-aboard-alliance-for-mass-adoption-of-the-blockchain-209bde271778)
