# BNB Greenfield Whitepaper



<figure><img src=".gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

The goal of the BNB Greenfield is to unleash the power of decentralized blockchain and storage technology on data ownership and data economy.

BNB Greenfield is not only a new blockchain in BNB but also an infrastructure and ecosystem targeting to facilitate the decentralized data economy. It tries to achieve it by easing the process to store and manage data access and linking data ownership with the massive DeFi context of BSC.

It focuses on 3 parts that differ from existing centralized and decentralized storage systems:

* It enables Ethereum-compatible addresses to create and manage both data and token assets.
* It natively links data permissions and management logic onto BSC as exchangeable assets and smart contract programs with all other assets.
* It provides developers with similar API primitives and performance as popular existing Web2 cloud storage.

It is expected that Greenfield will set up a playground and test field for new data economy and dApp models, which eventually becomes part of the foundation for Web3.

The white paper in this repository describes the main design and implementation of the platform. Many ideas are based on the great contributions of other leading protocols and teams. Please refer to the acknowledgment sections.

Any constructive opinions, ideas, and feedback are welcome.

Hope everyone enjoys the journey!

## Table of Content

* [Overview](intro/overview.md)
* [Part 1 Design of the BNB Greenfield and the Decentralized Storage Economy](part-1/part1/)
  * [1 Design Principles](part-1/part1/#1-design-principles)
  * [2 Assumptions](part-1/part1/#2-assumptions)
  * [3 The Architecture in General](part-1/part1/#3-the-architecture-in-general)
    * [3.1 Greenfield Core](part-1/part1/#31-greenfield-core)
    * [3.2 BNB Greenfield dApps](part-1/part1/#32-bnb-greenfield-dapps)
    * [3.3 The Cross-Chain with BSC](part-1/part1/#33-the-cross-chain-with-bsc)
    * [3.4 The Trinity](part-1/part1/#34-the-trinity)
  * [4 BNB Greenfield Core](part-1/part1/#4-bnb-greenfield-core)
    * [4.1 The BNB Greenfield Blockchain](part-1/part1/#41-the-bnb-greenfield-blockchain)
    * [4.2 The Storage Providers, SPs](part-1/part1/#42-the-storage-providers-sps)
    * [4.3 The Pair Synergy](part-1/part1/#43-the-pair-synergy)
  * [5 The Greenfield Data Storage](part-1/part1/#5-the-greenfield-data-storage)
    * [5.1 Data with Consensus](part-1/part1/#51-data-with-consensus)
      * [5.1.1 Accounts and Balance](part-1/part1/#511-accounts-and-balance)
      * [5.1.2 Validator and SP Metadata](part-1/part1/#512-validator-and-sp-metadata)
      * [5.1.3 Storage Metadata](part-1/part1/#513-storage-metadata)
      * [5.1.4 Permission Metadata](part-1/part1/#514-permission-metadata)
      * [5.1.5 Billing Metadata](part-1/part1/#515-billing-metadata)
    * [5.2 Off-Chain Payload Object Data Storage](part-1/part1/#52-off-chain-payload-object-data-storage)
      * [5.2.1 Primary and Secondary SPs](part-1/part1/#521-primary-and-secondary-sps)
      * [5.2.2 Data Redundancy](part-1/part1/#522-data-redundancy)
  * [6 Storage Economics and Its Primitives](part-1/part1/#6-storage-economics-and-its-primitives)
    * [6.1 Account Creation](part-1/part1/#61-account-creation)
    * [6.2 Data Object Creation](part-1/part1/#62-data-object-creation)
    * [6.3 Data Storage](part-1/part1/#63-data-storage)
    * [6.4 Data Read and Download](part-1/part1/#64-data-read-and-download)
    * [6.5 Permissions and Group](part-1/part1/#65-permissions-and-group)
    * [6.6 Fees and Payments](part-1/part1/#66-fees-and-payments)
    * [6.7 Data Integrity and Availability Challenge](part-1/part1/#67-data-integrity-and-availability-challenge)
    * [6.8 Data Delete](part-1/part1/#68-data-delete)
  * [7 Economy of Data Assets](part-1/part1/#7-economy-of-data-assets)
    * [7.1 Cross-Chain with BSC](part-1/part1/#71-cross-chain-with-bsc)
    * [7.2 Framework](part-1/part1/#72-framework)
    * [7.3 Communication Layer](part-1/part1/#73-communication-layer)
    * [7.4 Resource Mirror Layer](part-1/part1/#74-resource-mirror-layer)
      * [7.4.1 Resource Entity Mirror](part-1/part1/#741-resource-entity-mirror)
      * [7.4.2 Cross-Chain Operating Primitives](part-1/part1/#742-cross-chain-operating-primitives)
  * [8 "Not" Ending for the Design](part-1/part1/#8-not-ending-for-the-design)
    * [8.1 Acknowledgement](part-1/part1/#81-acknowledgement)
* [Part 2 Showcases in Labs](part-2/part2/)
  * [9 Showcases: Decentralized Storage](part-2/part2/#9-showcases-decentralized-storage)
    * [9.1 Web Hosting and Personal Cloud Drive](part-2/part2/#91-web-hosting-and-personal-cloud-drive)
    * [9.2 Data Availability Layer for Public Blockchain](part-2/part2/#92-data-availability-layer-for-public-blockchain)
      * [9.2.1 Layer 1 Blockchain Data Swapping](part-2/part2/#921-layer-1-blockchain-data-swapping)
      * [9.2.2 Data Availability Layer for the Layer 2 Rollups](part-2/part2/#922-data-availability-layer-for-the-layer-2-rollups)
      * [9.2.3 Snapshots and Block Data Backups](part-2/part2/#923-snapshots-and-block-data-backups)
  * [10 Showcases: New Ways of Digital Publishing](part-2/part2/#10-showcases-new-ways-of-digital-publishing)
    * [10.1 Grass-Root Digital Publishing](part-2/part2/#101-grass-root-digital-publishing)
    * [10.2 Data Market](part-2/part2/#102-data-market)
    * [10.3 Risk: Anti-Piracy](part-2/part2/#103-risk-anti-piracy)
  * [11 Showcases: User-Generated Content](part-2/part2/#11-showcases-user-generated-content)
    * [11.1 Anti-Monopoly and Anti-Censorship](part-2/part2/#111-anti-monopoly-and-anti-censorship)
    * [11.2 Token Curated Registries](part-2/part2/#112-token-curated-registries)
  * [12 Showcases: Personal Data Market](part-2/part2/#12-showcases-personal-data-market)
  * [13 From Showcases to Real Production](part-2/part2/#13-from-showcases-to-real-production)
* [Part 3 Simplified Technical Specifications](part-3/part3/)
  * [14 Ecosystem Players](part-3/part3/#14-ecosystem-players)
    * [14.1 Greenfield Validators](part-3/part3/#141-greenfield-validators)
    * [14.2 Storage Providers (SPs)](part-3/part3/#142-storage-providers-sps)
    * [14.3 Greenfield dApps](part-3/part3/#143-greenfield-dapps)
  * [15 User Identifier](part-3/part3/#15-user-identifier)
    * [15.1 User Balance](part-3/part3/#151-user-balance)
  * [16 Greenfield Blockchain](part-3/part3/#16-greenfield-blockchain)
    * [16.1 Token Economics](part-3/part3/#161-token-economics)
    * [16.2 Consensus and Validator Election](part-3/part3/#162-consensus-and-validator-election)
    * [16.3 Governance Transactions](part-3/part3/#163-governance-transactions)
      * [16.3.1 Create and Edit Validator](part-3/part3/#1631-create-and-edit-validator)
      * [16.3.2 Staking Reward Distribution](part-3/part3/#1632-staking-reward-distributio-n)
      * [16.3.3 Create Storage Provider](part-3/part3/#1633-create-storage-provider)
      * [16.3.4 Remove Storage Provider](part-3/part3/#1634-remove-storage-provider)
  * [17 Storage MetaData Models](part-3/part3/#17-storage-metadata-models)
    * [17.1 Bucket](part-3/part3/#171-bucket)
    * [17.2 Object](part-3/part3/#172-object)
    * [17.3 Group](part-3/part3/#173-group)
    * [17.4 Permission](part-3/part3/#174-permission)
      * [17.4.1 Ownership](part-3/part3/#1741-ownership)
      * [17.4.2 Permission Definitions](part-3/part3/#1742-permission-definitions)
      * [17.4.3 Permission Removal](part-3/part3/#1743-permission-removal)
      * [17.4.4 Examples](part-3/part3/#1744-examples)
  * [18 Payload Storage Management](part-3/part3/#18-payload-storage-management)
    * [18.1 Segments](part-3/part3/#181-segments)
    * [18.2 Erasure Code and Data Redundancy](part-3/part3/#182-erasure-code-and-data-redundancy)
      * [18.2.1 Data Redundancy Design](part-3/part3/#1821-data-redundancy-design)
      * [18.2.2 Erasure Code](part-3/part3/#1822-erasure-code)
        * [18.2.2.1 Encoding](part-3/part3/#18221-encoding)
        * [18.2.2.2 Decoding: Data Recovery](part-3/part3/#18222-decoding-data-recovery)
  * [19 Data Availability Challenge](part-3/part3/#19-data-availability-challenge)
    * [19.1 The Initial Data Integrity and Redundancy Metadata](part-3/part3/#191-the-initial-data-integrity-and-redundancy-metadata)
    * [19.2 Data Availability Challenge Process](part-3/part3/#192-data-availability-challenge-process)
  * [20 Storage Transactions](part-3/part3/#20-storage-transactions)
  * [21 Billing and Payment](part-3/part3/#21-billing-and-payment)
    * [21.1 Concepts and Formulas](part-3/part3/#211-concepts-and-formulas)
      * [21.1.1 Terminology](part-3/part3/#2111-terminology)
      * [21.1.2 Formula](part-3/part3/#2112-formula)
      * [21.1.3 Types and Interfaces](part-3/part3/#2113-types-and-interfaces)
    * [21.2 Key Workflow](part-3/part3/#212-key-workflow)
      * [21.2.1 Deposit and Withdrawal](part-3/part3/#2121-deposit-and-withdrawal)
      * [21.2.2 Payment Stream](part-3/part3/#2122-payment-stream)
      * [21.2.3 Forced Settlement](part-3/part3/#2123-forced-settlement)
      * [21.2.4 Payment Account](part-3/part3/#2124-payment-account)
      * [21.2.5 Account Freeze and Resume](part-3/part3/#2125-account-freeze-and-resume)
      * [21.2.6 Storage Fee Price and Adjustment](part-3/part3/#2126-storage-fee-price-and-adjustment)
  * [22 Cross-Chain Models](part-3/part3/#22-cross-chain-models)
    * [22.1 Communication Channels and Packages](part-3/part3/#221-communication-channels-and-packages)
      * [22.1.1 Vote Poll](part-3/part3/#2211-vote-poll)
      * [22.1.2 Channel and Sequence](part-3/part3/#2212-channel-and-sequence)
      * [22.1.3 Reliability Protocol](part-3/part3/#2213-reliability-protocol)
      * [22.1.4 Validator Update](part-3/part3/#2214-validator-update)
    * [22.2 Economic](part-3/part3/#22-2-economic)
      * [22.2.1 Fee and Reward of Cross-Chain Packages](part-3/part3/#2221-fee-and-reward-of-cross-chain-packages)
      * [22.2.2 Race to Deliver Cross-Chain Packages](part-3/part3/#2222-race-to-deliver-cross-chain-packages)
      * [22.2.3 Callbacks and Limited Gas](part-3/part3/#2223-callbacks-and-limited-gas)
      * [22.2.4 Cross-Chain Infrastructure Contracts on BSC](part-3/part3/#2224-cross-chain-infrastructure-contracts-on-bsc)
    * [22.3 Error and Failure Handling](part-3/part3/#223-error-and-failure-handling)
  * [23 SP APIs](part-3/part3/#23-sp-apis)
    * [23.1 Universal Endpoint](part-3/part3/#231-universal-endpoint)
      * [23.1.1 URI Standard](part-3/part3/#2311-uri-standard)
      * [23.1.2 HTTPS REST API](part-3/part3/#2312-https-rest-api)
      * [23.1.3 P2P RPC](part-3/part3/#2313-p2p-rpc)
    * [23.2 List Operations](part-3/part3/#232-list-operations)
* [Ending](finish-words/ending.md)

## License

All the content are licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
