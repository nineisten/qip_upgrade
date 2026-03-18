```
flowchart TD
    Start["`Start: Issuer logs into platform`"] --> Create["`Create New ICO`"]

    Create --> Upload["`Upload rich project details
- Thumbnail - Website/whitepaper/social/repo links
- Issuer bio/verified status/contact`"]

    Upload --> Pay["`Pay mandatory setup fee
100M Qubic to SC reserve / Treasury seed`"]

    Pay --> Config["`Configure optional protections and access`"]
    Config --> Vesting["`Flexible Vesting
- Tokens and revenue streams
- Per-wallet configurable
- 30 days / 3-6-12-18 months / custom
- Staggered per epoch`"]
    Config --> Burn["`Optional Token Burn
- Unsold tokens to burn address at end`"]
    Config --> Clawback["`Optional Clawback / Rug Protection
- Percentage of treasury 30 to 50 percent recommended
- Trigger 65 percent investor vote OR 6+ months inactivity
- Burn-to-Claim refund`"]
    Config --> DevTranche["`Early Dev Access Tranche
- 0 to 40 percent recommended maximum 25 percent
- Immediate or time-based release to team
- Purpose notes required`"]

    Vesting & Burn & Clawback & DevTranche --> Review["`Review all settings
- Trust Score preview`"]
    Review --> Launch["`Launch ICO to Live on platform`"]

    Launch --> InvestorBrowse["`Investor browses ICO list
- Sort/filter by Trust Score
- See thumbs up/down aggregate`"]

    InvestorBrowse --> ViewPage["`View detailed ICO page
- Full metadata and links
- Live QIP dividend/share stats
- Phase snapshots and reports
- Current thumbs voting`"]

    ViewPage --> Vote["`Give thumbs up / down
- Influences Trust Score`"]

    ViewPage --> Participate["`Participate: Buy tokens
- Pay Qubic to Treasury
- Vesting rules applied per wallet
- Clawback percentage escrowed if enabled`"]

    Participate --> DuringICO["`ICO active phase
- Funds accumulate in Treasury
- Dev Tranche releases as configured
- Team builds and delivers`"]

    DuringICO --> EndICO["`ICO ends / fundraising closed`"]

    EndICO --> ClawbackDecision["`Clawback Triggered`"]
    ClawbackDecision -->|Yes| ClawbackYes["`Clawback Activated
- Snapshot of ABC holders
- Refund Pool equals Treasury plus Escrow
- Minus already-released Dev Tranche`"]
    ClawbackYes --> ClaimWindow["`Claim window opens 90 to 180 days`"]

    ClaimWindow --> InvestorClaim["`Investor calls claimClawbackRefund
- Contract burns their ABC tokens
- Receives pro-rata QUBIC refund`"]
    InvestorClaim --> RefundEnd["`Refund complete
- Unclaimed funds auto-burn or to Dev Fund`"]

    ClawbackDecision -->|No| ClawbackNo["`No clawback triggered`"]
    ClawbackNo --> PostActions["`Post-ICO actions`"]

    PostActions --> BurnAction["`If burn enabled Unsold tokens to burn address`"]
    PostActions --> VestingRelease["`Apply vesting schedule
- Staggered revenue release per epoch
- Final token unlock at end`"]
    PostActions --> DevFund["`Dev Fund receives extra 2.5 percent of QIP redistributions
- Ongoing from future revenue`"]

    VestingRelease & BurnAction & DevFund --> SuccessEnd["`End Investors and team receive vested funds/tokens
- Project continues or fails gracefully`"]