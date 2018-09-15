![](http://dogecon.fun/images/partydoge.jpeg)

# Tenzorum Documentation

Tldr; Tenzorum is building ux infrastructure for web3. [Our whitepaper](https://github.com/Tenzorum/whitepaper-draft1/blob/master/Tenzorum%20Project%20Whitepaper%20Draft%201.pdf)

Aiming to help craft the best user experience there can be by any means possible.

## What are the main projects we are working on?

**Gas relayer service node protocol** — TSNN (Tenzorum Service Node Network)

Protocol for recieving offchain meta-transactions and executing them on behalf of users. Service nodes are compensated for this delegated transactions service. This enables a sexier new form of user experience that was previously not possible.

[Docs on the TSNN](https://github.com/Tenzorum/.documentation/blob/master/TSNN)

**Web3 Key Management SDK** - IPAS (Inter-Planetary Access System)

A SDK that is used to interface with the TSNN to use meta-transactions. Also includes other fun things such as standardised multi-sig wallets with key permissioning that uses meta-transactions, 725 identity tenzorum identity kit, universal login system, ENS subdomain factory, key recovery solutions and blockchain notifications API kit. This is essentially a fun party bag that is not only used to implement and use the TSNN but also used to implement other UX infrastructure.

[Docs on IPAS](https://github.com/Tenzorum/.documentation/blob/master/IPAS)

## Repositories Overview

**TSNN (Tenzorum Service Node Network)**

[Tenzorum Service Node (TSNN)](https://github.com/Tenzorum/TSNN-Service-Node) - service node client

[Service Node Network Interface and Tx selection](https://github.com/Tenzorum/TSNN-network-interface) - network interface & tx propagation

[TSNN SDK](https://github.com/Tenzorum/TSNN-client-sdk) - relaying txs to TSNN

[Meta-Tx TSNN standard](https://github.com/Tenzorum/meta-transaction-format-share)

**IPAS (Inter-Planetary Access System)**

[ENS subdomain factory](https://github.com/Tenzorum/IPAS-ens-subdomain-factory) - makes subdomains

[Personal multi-sig](https://github.com/Tenzorum/IPAS-personal-wallet-contracts) - multi-sig with TSNN SDK implementation

[Mobile IPAS interface](https://github.com/Tenzorum/IPAS-mobile-portal) - mobile front end to use IPAS and TSNN Multi-sigs

[Chrome extention key manager](https://github.com/Tenzorum/IPAS-chrome_extension) - chrome ext. for multisig identity keys

[Key manager prototype](https://github.com/Tenzorum/IPAS-momentum-browser) - client side key manager

[Key manager login prototype](https://github.com/Tenzorum/IPAS-login-prototype) - key manager login idea

## How to contribute

Join us on here on telegram...
