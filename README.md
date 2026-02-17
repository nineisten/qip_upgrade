
## Summary

This outline introduces a comprehensive set of enhancements to the Qubic ICO platform aimed at improving trust, transparency, long-term alignment, and ecosystem sustainability. Key additions include:

A mandatory 100M Qubic setup fee that seeds smart-contract liquidity
A permanent 2.5% developer fund contribution from all QIP redistributions
Flexible, per-wallet vesting schedules for both tokens and revenue streams
Optional on-chain token burning of unsold supply
Rich project metadata, community feedback (thumbs), live dividend visibility, and an automatically calculated Trust Score

Together, these features make it significantly easier for investors to evaluate ICO quality and risk, while giving serious issuers stronger tools to signal commitment and differentiate themselves from low-effort or speculative projects.

### 1. Outline of Upgrades

**A. ICO Setup Fee**  
- Mandatory 100 million Qubic fee paid by the issuer at ICO creation.  
- Fee is automatically routed to the smart-contract (SC) reserve to feed execution fees.

**B. Development Fund Allocation**  
- Add a fixed extra 2.5 % slice to QIP SC redistribution in addition to existing 5%.  
- This 2.5 % flows to a dedicated Development Fund address/wallet.

**C. Vesting Periods (Optional but per-wallet configurable)**  
- Applies to both tokens and project revenue wallets.  
- Pre-defined options: 30 days, 3 months, 6 months, 1 year, 1.5 years + custom duration.  
- Revenue vesting: releases staggered per epoch; full remaining balance unlocked at end of period.  
- Token vesting: all unsold/remaining tokens stay locked until the final epoch of the period.  
- Can be set independently for each participating wallet (issuer can assign different vesting to different buyers or revenue streams).

**D. Optional Burn Mechanism**  
- At ICO end, instead of returning unsold tokens to the issuer, the contract can send them directly to a designated burn address (configurable at launch).  
- Burn is irreversible and publicly visible on-chain.

**E. UI + Server API Extensions**  
- New fields in ICO creation / listing API:  
  – Token thumbnail (image upload or URL)  
  – Project links (website, whitepaper, socials, repo)  
  – Issuer information (name, verified status, bio, contact)  
  – QIP Share dividend tracking (pulls live stats from QIP contract)  
  – Enhanced reporting: automatic snapshots of raised Qubic, token distribution, phase-end summaries  
- User interaction layer:  
  – Thumbs-up / thumbs-down per ICO (stored server-side, visible to all)  
- Trust Score (0–100) calculated server-side from weighted factors:  
  + Clear project descriptions → +  
  + Vesting > 3 months → +  
  + Vesting = 3 months → neutral  
  + Vesting < 3 months (shorter = bigger penalty) → –  
  + Token burn enabled → +  
  + Project links provided → +  
  + Multiple revenue wallets → + (adds transparency)  
  + No project details → –  
  + Supply pre-sold on exchange before ICO → –  
  + Community thumbs-up count → +  
  + Community thumbs-down count → –  

### 2. User Flow (Mermaid Flowchart)

```mermaid
%%{init: {'theme': 'neutral', 'themeVariables': {'primaryColor': '#ffffff', 'primaryTextColor': '#000000', 'primaryBorderColor': '#000000', 'lineColor': '#666666', 'secondaryColor': '#f0f0f0', 'tertiaryColor': '#e0e0e0'}}}%%
flowchart TD
    A[Start: Issuer logs into platform] 
    --> B[Create New ICO]

    B --> C[Upload project details<br/>• Thumbnail<br/>• Links & description<br/>• Issuer information]
    C --> D[Pay mandatory setup fee<br/>100 m Qubic → SC reserve]

    D --> E{Optional features}
    E --> F[Configure vesting<br/>• Tokens & revenue wallets<br/>• Periods: 30d / 3mo / 6mo / 1y / 1.5y / custom<br/>• Staggered epoch release]
    E --> G[Enable burn mechanism<br/>Remaining supply → burn address]
    E --> H[Add multiple revenue wallets<br/>(for transparency)]

    F & G & H --> I[Review & Launch ICO]

    I --> J[ICO Live on platform]

    J --> K[Investor browses ICO list<br/>• Sorted/filtered by Trust Score]
    K --> L[View ICO page<br/>• Thumbnail + full details<br/>• Issuer info<br/>• QIP dividend tracker<br/>• Phase-end snapshot reports<br/>• Live thumbs up/down]
    L --> M[Investor gives thumbs up/down]
    M --> N[Calculate & display Trust Score<br/>based on all criteria above]
    L --> O[Participate → Buy tokens<br/>(vesting rules applied per wallet)]

    O --> P[ICO ends]

    P --> Q{Post-ICO actions}
    Q --> R[If burn enabled → remaining tokens burned]
    Q --> S[Apply vesting schedule<br/>• Staggered revenue release per epoch<br/>• Final unlock of remaining tokens]
    Q --> T[Dev Fund receives extra 2.5 % of any QIP redistributions]

    R & S & T --> End[End: All parties receive funds/tokens]

    classDef box fill:#ffffff,stroke:#000000,stroke-width:2px,color:#000000,rx:8,ry:8
    class A,B,C,D,E,F,G,H,I,J,K,L,M,N,O,P,Q,R,S,T,End box

    style E fill:#f0f0f0,stroke:#666666
    style N fill:#e0e0e0,stroke:#666666
```
### Conclusion

The proposed upgrades represent a balanced step toward professionalizing the Qubic ICO ecosystem without imposing excessive mandatory restrictions on issuers. By combining on-chain mechanisms (fee → reserve, vesting, burn, dev fund) with off-chain trust signals (metadata, community ratings, Trust Score), the platform can foster higher-quality projects, reduce rug-pull incentives, and increase overall participant confidence.
If implemented, these changes would likely:

Attract more serious teams and long-term-oriented investors
Improve capital allocation efficiency within the Qubic network
Create a sustainable funding stream for ongoing protocol & platform development

Overall, the package offers meaningful investor protection and issuer accountability while preserving the permissionless and innovative spirit of decentralized fundraising on Qubic.