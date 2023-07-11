---
title: "Uni v4 : A new form of liquidity"
publishDate: "25 june 2023"
description: "A look on the promising announcement made by uniswap ! Uni v4 and hooks"
tags: ["DeFi", "Economics","Liquidity"]
author: "Delioos"
ogImage: "../../assets/uniswapLogo.png"
---
__@Delioos__
# Target audience
Before I begin, I'd like to point out that this article is aimed at an audience with a relatively solid knowledge base of DeFi.

# uni v3
If you'd like to take a closer look at the current version of Uniswap, I recommend the blog post made by Uniswap <a href="https://blog.uniswap.org/uniswap-v3"> here </a>.
# uni v4

On June 13, 2023, Uniswap shared its vision for v4 . Here's a sneak preview of this major upcoming update, which will have a major impact on the current liquidity system.
<img src="../../assets/uniswapLogo.png" alt="uniswap logo (unicorn) on a colorful background">
## **HOOKS : PERSONALIZED POOLS**

The major news is the introduction of hooks, a new smart contract linked to liquidity pool, that will interact along its life cycle (before or after  a token exchange, for an example)

This module is the key to future innovations:

- Dynamic fees based on volatility or other data;
- Limit order directly on-chain;
- Deposit of liquidity outside the range in lending protocols;
- Personalized on-chain oracles;
- LP fees are automatically rewarded in LP positions;
- Internalized MEV profits are distributed to LPs. Redistribution of internalized SRM profits to liquidity providers.
- Time-weighted average market maker;

# Pool optimization and flexibility

## Dynamic fees

In order to provide liquidity providers with even greater flexibility, Uniswap offers adaptive fees based on pair volatility. This avoids having to close and reopen a position if the asset's status changes. At present, we have to price the fees charged when the pool is created (0.01 / 0.05 / 0.3 / 1%, with an indication of the % of pools on this or that fee scale. We tend to say 0.01 / 0.05 for stable stable, 0.05 / 0.3 for known assets, and 1% for more degen pairs).

## LP fees autocompound

Once again emphasizing optimization, the unicorn offers "autocompounding" of the fees earned thanks to the liquidity you provide: rather than claiming your due and modifying your position, the protocol will take care of reinjecting it in real time. The total gain is considerable, since there are fewer position change fees, and we gain in fees collected as the liquidity provided becomes increasingly important.

## Customized oracles

The hooks would also bring the possibility of integrating new oracles (support for transferring info between the blockchain and the outside world). This means that developers will be able to integrate their own logic for obtaining price data or other information, possibly from multiple sources or according to their own algorithms, offering greater flexibility and potential for innovation.

<img alt="abstract image of geometrical shapes forming an eye" src="../../assets/oracles.png">

# Architecture modification

## lower-cost pools

reduced opening costs: using a special programming structure: the **singleton.**

"In its simplest form, 'singleton' architecture is a design method which ensures that only one instance of an entity exists. Here, this applies to pools, and more specifically to the linked smart contract. In v3, each provider has one smart contract per poo.  By implementing a single smart contract, overloaded with hooks, overall costs can be reduced.

To delve a little deeper into the techno, we can mention the addition of the "flash accounting" principle.

In general terms, a transac means the transfer of tokens from an A address to a B address. To make this exchange, tokens are transferred from the user's wallet to the pool, then from the pool to the recipient. Each transfer is registered and validated in the chain, consuming a significant amount of gas.

In flash accounting, rather than transferring assets at each stage, the system tracks net asset balances. If multiple txes are performed in a single block, the system only transfers the net balance, so this could be smaller (or potentially zero if the same amount is bought and resold), than the total of the individual txes accumulated.

However, the technology needs to be proven (accurate and secure), as this abstraction lightens the chain but poses a dilemma in terms of traceability accuracy... However, this doesn't take away the trustless aspect, as all smart contracts remain open source, so there's no need to worry.

## Change of related license

Once again, Uniswap has chosen to retain ownership, and prohibit commercial use by forking their protocol, for 4 years (maximum) thanks to a Business Source 1.1 license. Unless Uniswap Governance or Labs makes a change, at the end of this period the code will become open source under the GPL.

# My analysis

The DeFi unicorn is once again positioning itself as a leader in decentralized protocol innovation, focusing on user experience and flexibility. Although becoming a liquidity provider requires relatively solid technical knowledge, I think these developments are a further step towards the recognition of DeFi as a serious and stable alternative to tradfi, for an increasingly wide audience.
