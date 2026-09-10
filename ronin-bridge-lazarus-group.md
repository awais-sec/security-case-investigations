# Case Investigation: Ronin Bridge / Axie Infinity / Lazarus Group Ethereum Investigation

**Class Assignment No. 2**
**Submitted by:** Awais Ahmed (Sp-23/BS DFCS/008)

## 1. Case Title

Ronin Bridge / Axie Infinity / Lazarus Group Ethereum Investigation

## 2. Investigation Objective

The objective of this investigation is to analyze Ethereum blockchain activity related to the Ronin Bridge exploit, examine smart contract interactions, identify major transactions involving ETH and USDC, verify sanctions listings, and understand the limitations of public blockchain evidence.

## 3. Tools and Resources Used

- Ronin Network Postmortem
- Etherscan Blockchain Explorer
- OFAC Sanctions Page
- U.S. Treasury Tornado Cash Release

## 4. Verified Case Facts (Summary)

The Ronin Bridge exploit occurred on 23 March 2022 and was discovered on 29 March 2022. The attacker drained 173,600 ETH and 25.5 million USDC. The attack was executed by compromising five out of nine validator private keys, allowing forged withdrawal approvals. The exploit was carried out in two major transactions. The address involved is publicly labeled as the Ronin Bridge Exploiter and is sanctioned by OFAC under the Lazarus Group.

## 5. Case Facts Table

| Fact | Source | Relevance |
|---|---|---|
| Attack date: 23 March 2022 | Ronin Postmortem | Timeline |
| Discovered: 29 March 2022 | Ronin Postmortem | Detection delay |
| 173,600 ETH stolen | Ronin Postmortem | Major loss |
| 25.5M USDC stolen | Ronin Postmortem | Major loss |
| 5/9 validators compromised | Ronin Postmortem | Attack method |
| 2 transactions used | Ronin Postmortem | Execution |

## 6. Address Investigated

**Address:** `0x098B716B8Aaf21512996dC57EB0615e2383E2f96`

- Label: Ronin Bridge Exploiter
- Category: Exploit
- Sanctions: OFAC-Sanctioned

The address and its label were verified on Etherscan (see Figure 1).

## 7. Why Current Balance Is Not Reliable

The current balance of an Ethereum address can change over time due to further transactions. Therefore, it does not represent the original stolen amount, and investigators must rely on historical transaction data.

## 8. ETH Transaction Analysis (173,600 ETH)

| Field | Details |
|---|---|
| Hash | `0xc28fad5e8d5e0ce6a2eaf67b6687be5d58113e16be590824d6cfa1a94467d0b7` |
| Status | Success |
| Time | 23 Mar 2022 01:29:09 UTC |
| From | Exploiter Address |
| To | Ronin Bridge Contract |
| Function | `withdrawERC20For` |
| Internal Transfer | 173,600 ETH |
| Value Field | 0 ETH |
| Fee | 0.019899 ETH |

**Explanation:** this is not a normal transfer. It is a smart contract interaction, where ETH movement appears in internal transactions, not in the main value field. This indicates interaction with a smart contract rather than a direct wallet-to-wallet transfer.

The internal transfer of 173,600 ETH is visible on Etherscan (see Figure 2).

## 9. USDC Transaction Analysis (25,500,000 USDC)

| Field | Details |
|---|---|
| Hash | `0xed2c72ef1a552ddaec6dd1f5cddf0b59a8f37f82bdda5257d9c7c37db7bb9b08` |
| Status | Success |
| Time | 23 Mar 2022 01:31:04 UTC |
| From | Exploiter Address |
| Interacted With | Ronin Bridge |
| Token | USDC |
| Amount | 25,500,000 |
| Value Field | 0 ETH |
| Fee | 0.0219782 ETH |

The ERC-20 transfer of 25,500,000 USDC is shown (see Figure 3).

## 10. Comparison (ETH vs. USDC)

The ETH transaction shows asset movement through internal transactions, while the USDC transfer appears under ERC-20 token transfers. Both transactions show 0 ETH in the value field, demonstrating that Ethereum investigations require deeper analysis beyond basic transaction values.

## 11. OFAC Sanctions Verification

| Field | Entry |
|---|---|
| Address | `0x098B716B8Aaf21512996dC57EB0615e2383E2f96` |
| Source | OFAC |
| Listed Entity | Lazarus Group |
| Present | Yes |
| Date | 22 April 2022 |

The address is listed under sanctions (see Figure 4).

## 12. Tornado Cash (Mixer Explanation)

A cryptocurrency mixer like Tornado Cash obscures transaction origins by pooling and redistributing funds. This makes tracing difficult but does not erase previous blockchain records, meaning earlier transactions remain visible for forensic analysis.

## 13. Transaction Evidence Table

| Date | Hash | Asset | Amount | From | To | Source |
|---|---|---|---|---|---|---|
| 23 Mar 2022 | `c28f...` | ETH | 173,600 | Exploiter | Ronin Bridge | Etherscan |
| 23 Mar 2022 | `ed2c...` | USDC | 25,500,000 | Exploiter | Ronin Bridge | Etherscan |

## 14. Fund Flow Diagrams

**ETH Flow:**
```
Compromised Validators → Forged Approval → Ronin Bridge → 173,600 ETH → Exploiter Address
```

**USDC Flow:**
```
Compromised Validators → Forged Approval → Ronin Bridge → 25.5M USDC → Exploiter Address
```

## 15. Confirmed Facts

| Fact | Source |
|---|---|
| Attack occurred | Ronin |
| ETH stolen | Etherscan |
| USDC stolen | Etherscan |
| Address labeled exploiter | Etherscan |
| Address linked to Lazarus | OFAC |

## 16. Limitations

| Overclaim | Reality |
|---|---|
| Identity proven | Not from blockchain alone |
| Value field shows theft | Must check internal/ERC20 |
| Current balance shows loss | Not reliable |
| Mixers remove traces | Only obscure |

## 17. Conclusion

The Ronin Bridge exploit demonstrates how smart contract vulnerabilities can be exploited to drain large amounts of cryptocurrency. Public blockchain data confirms the transaction flow and amounts stolen, while OFAC provides attribution to Lazarus Group. However, blockchain evidence alone cannot independently verify real-world identity.

## 18. Screenshots Annexure

*All screenshots were accessed on 6 May 2026 (UTC).*

---
*Source: Awais Ahmed's own class assignment, Investigating Cryptocurrencies module.*
