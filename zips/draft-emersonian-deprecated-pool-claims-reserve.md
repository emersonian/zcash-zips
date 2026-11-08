    ZIP: Unassigned
    Title: Update to ZIP 1016: Deprecated-Pool Claims Reserve
    Owners: Emerson <TBD>
    Status: Draft
    Category: Process
    Created: 2026-11-08
    License: MIT
    Discussions-To: <URL TBD>
    Updates: 1016


# Terminology

The key words "MUST", "MUST NOT", "SHALL", "SHOULD", "SHOULD NOT", and "MAY"
in this document are to be interpreted as described in BCP 14 [^BCP14] when,
and only when, they appear in all capitals.

The terms "Mainnet" and "Testnet" in this document are to be interpreted as
defined in the Zcash protocol specification [^protocol-networks].

The terms "Coinholder-Controlled Fund" and "Key-Holder Organizations" in this
document are to be interpreted as described in ZIP 1016 [^zip-1016], as
amended by any ZIP that updates the membership of the Key-Holder Organizations
(see for example [^draft-mcgee-keyholders]).

The term "Sprout chain value pool balance" is to be interpreted as described
in ZIP 209 [^zip-0209].

"ZEC" refers to the native currency of Zcash on Mainnet.

The terms below are to be interpreted as follows:

Coinholder-amount voting round

: A coinholder vote held under ZIP 1016 [^zip-1016-disbursement], in which each
  ballot is weighted by the amount of ZEC that the voter proves control of,
  conducted under the rules for such votes that are in effect at the time the
  vote is held.

Adoption Vote

: The coinholder-amount voting round, described in [Adoption](#adoption), in
  which coinholders vote on whether to adopt this ZIP.

Adoption Date

: The date on which the Key-Holder Organizations publish the certified result of
  an Adoption Vote that approves this ZIP.

Deprecated Pool

: Any chain value pool (shielded or transparent) on Mainnet from which a network
  upgrade has made it impossible, under the consensus rules then in effect, to
  spend funds that were validly held in that pool before the network upgrade
  activated. This includes, but is not limited to, the Sprout pool from the
  activation of NU7 [^zip-0259] [^zip-2003]. It also includes any pool that a
  future network upgrade switches off in this way, for example the Sapling or
  Orchard pools under the scenario described in ZIP 2005 [^zip-2005-effects].

  A pool stops being a Deprecated Pool if, and for as long as, the consensus
  rules again allow the affected funds to be spent or moved by their holders.

Stranded Funds

: Funds that were validly held in a Deprecated Pool at the activation height of
  the network upgrade that made that pool a Deprecated Pool, and that cannot be
  spent because of that network upgrade.

Deprecated-Pool Holder

: Any person or entity (including, but not limited to, individuals, exchanges,
  custodians, trusts, estates, and other organizations) that held the spending
  authority for Stranded Funds at the activation height of the network upgrade
  that stranded them, or that is a lawful successor to that spending authority.

Claims Reserve

: The amount of ZEC set aside under this ZIP, as specified in [Reserve
  amount](#reserve-amount), together with any later top-up required by
  [Shortfall at the Adoption Date](#shortfall-at-the-adoption-date).

Reserve Account

: The separate account that holds the Claims Reserve, as specified in [Reserve
  Account](#reserve-account).

Claims Process ZIP

: A future ZIP, described in [Claims process (TBD)](#claims-process-tbd), that
  specifies how Deprecated-Pool Holders can make claims against the Claims
  Reserve.


# Abstract

This ZIP orders the Key-Holder Organizations to set aside 8,000 ZEC from the
Coinholder-Controlled Fund (approximately US$10 million at the time of
writing) at the time this ZIP is approved in a coinholder-amount voting round.
The set-aside ZEC is to be held in a separate Reserve Account that is not
commingled with other Coinholder-Controlled Fund assets, and is to be used
only to pay future claims by holders of ZEC in deprecated pools, including but
not limited to entities holding ZEC in the Sprout pool.

The process by which holders make and prove claims is left to a future Claims
Process ZIP. Until that ZIP is Active, no claims are paid, and the Claims
Reserve stays at rest. This ZIP itself discloses nothing about deprecated-pool
holders. The privacy questions raised by proving past ownership of Sprout
notes are left to the Claims Process ZIP.


# Motivation

NU7 disallows version 4 transactions [^zip-2003]. Because Sprout transfers can
only be represented by version 4 transactions, funds remaining in the Sprout
pool become unspendable once NU7 activates [^zip-0259]. As of 21 October 2026,
about 22,300 ZEC remained in the Sprout pool [^zip-0218-pools], which is worth
roughly US$28 million at the price used in this ZIP.

ZIP 2003 expressly does not unissue, burn, or otherwise make Sprout funds
permanently unavailable, and it leaves open "the theoretical possibility of
re-enabling v4 transactions, or of adding another facility to retrieve these
funds if the Zcash community considers it worthwhile" [^zip-2003]. It also
says the ability to spend Sprout funds may never be re-enabled. That leaves
Sprout holders with no assured remedy.

Some of these holders may have had little practical opportunity to move their
funds. The deprecation of zcashd removed the only maintained software that
still provided wallet functionality for Sprout [^zip-2003], and NU7 waived the
usual requirement that the activation height exceed the deprecation height of
the last unsupported software release, along with the recommendation of about
three months' notice after the first supporting release [^zip-0259]. Holders
who were offline, who held keys in cold storage, who were incapacitated, or who
hold funds as part of an estate or under a custodial arrangement may only learn
of the change after their funds have been stranded.

The same problem may recur. ZIP 2005 anticipates that the legacy Orchard,
Sapling, and Sprout protocols may be switched off to protect against
discrete-logarithm-breaking adversaries, which would render any remaining funds
in those pools permanently unspendable [^zip-2005-effects]. A standing,
pool-neutral reserve and a single claims framework are simpler and fairer than
a separate debate each time a pool is retired.

Making a remedy available, even a partial one, supports the credibility of
Zcash as a store of value. A holder should not lose funds solely because
the network removed the protocol that their funds were held under. The
Coinholder-Controlled Fund is the natural source for such a remedy: it is
Protocol-defined Ecosystem Funding, coinholders control its use, and the
change that strands the funds was adopted for the benefit of the whole
ecosystem.

Setting the reserve aside at the time of the vote, rather than when a claims
process is ready, ensures that the funds remain available while the claims
process is designed, and that later grant decisions cannot spend them.


# Privacy Implications

This ZIP does not change the consensus rules and does not itself disclose
anything about Stranded Funds or their holders.

A claims process could have significant privacy implications: proving
historical ownership of a Sprout note could link a claimant to past
transactions, and any identity checks would link a claimant to a legal
identity. The Claims Process ZIP will need to minimize what a claimant has to
reveal and what is published about claims.

Publishing the Reserve Account address or viewing keys reveals the reserve's
balance and payments, but not who receives them if payments are made to
shielded addresses.


# Requirements

* Once this ZIP is approved, a fixed amount of ZEC is reserved for claims by
  Deprecated-Pool Holders, and cannot be used for any other purpose.
* The reserved ZEC is held in an account separate from all other
  Coinholder-Controlled Fund assets, and its balance and movements are publicly
  verifiable.
* The reserved ZEC is under at least the same multi-party custody and security
  as the rest of the Coinholder-Controlled Fund.
* No claim is paid until a claims process has been specified and adopted.
* The existence of the Claims Reserve does not depend on any consensus change.


# Non-requirements

* This ZIP does not specify the claims process, eligibility proofs, claim
  windows, or payout formula. These are left to the Claims Process ZIP.
* This ZIP does not propose re-enabling version 4 transactions, re-enabling
  Sprout spends, or any other consensus change.
* This ZIP does not propose unissuing, burning, or reissuing Stranded Funds,
  or changing how they are treated in $\mathsf{IssuedSupply}$ for the purpose
  of the Network Sustainability Mechanism [^zip-2003].
* This ZIP does not guarantee that Deprecated-Pool Holders will be compensated
  in full, or at all.
* This ZIP does not change the ZCG funding stream or ZCG governance.


# Specification

## Adoption

This ZIP takes effect only if it is approved in a coinholder-amount voting
round held under the rules for such votes that are in effect at the time
(as of writing, a minimum of 420,000 ZEC voted with a simple majority in
favor [^zip-1016-disbursement]).

The Key-Holder Organizations SHOULD place this ZIP on the ballot for the first
coinholder-amount voting round held at least 30 days after this ZIP is
submitted for community review, consistent with the 30-day review requirement
in ZIP 1016 [^zip-1016-disbursement].

For the purpose of the ZIP 1016 veto process, the Adoption Vote is not a vote
on a grant application. A Key-Holder Organization that believes that complying
with this ZIP would violate any of its legal or reporting obligations SHALL
declare this publicly, with a thorough rationale, before the Adoption Vote
opens, and SHOULD propose changes that would remove the conflict.

The Key-Holder Organizations SHALL publish the certified result of the Adoption
Vote. If the Adoption Vote approves this ZIP, the date of that publication is
the Adoption Date.

## Reserve amount

The Claims Reserve is 8,000 ZEC (800,000,000,000 zatoshi).

This amount is fixed in ZEC and MUST NOT be adjusted for any change in the
ZEC/USD exchange rate between the writing of this ZIP, the Adoption Vote, and
any later claim.

Non-normative note: The amount was chosen to approximate US$10 million. At
US$1,262.40 per ZEC (CoinGecko, 2026-11-08 [^coingecko-zec]), US$10 million is
about 7,921 ZEC, which is rounded up to 8,000 ZEC (about US$10.1 million at
that price). Fixing the amount in ZEC means that the reserve is known exactly
when coinholders vote, does not require selling or buying ZEC, and does not
depend on choosing a price oracle.

## Encumbrance at the time of the vote

From the moment the Adoption Vote closes with a result approving this ZIP,
8,000 ZEC of the Coinholder-Controlled Fund held by the Key-Holder
Organizations is encumbered for the Claims Reserve.

From that moment, and until the Claims Reserve has been transferred to the
Reserve Account in full, the Key-Holder Organizations MUST NOT sign any
transaction spending Coinholder-Controlled Fund assets, other than:

* a transaction that transfers funds to the Reserve Account; or
* a payment for a grant that was approved in an earlier coinholder-amount
  voting round, if after that payment the funds remaining under the
  Key-Holder Organizations' control are at least 8,000 ZEC plus any amount
  still to be transferred under
  [Shortfall at the Adoption Date](#shortfall-at-the-adoption-date).

The Key-Holder Organizations MUST transfer the Claims Reserve to the Reserve
Account no later than 14 days after the Adoption Date.

## Funding source

The Claims Reserve MUST be funded from Coinholder-Controlled Fund assets that
the Key-Holder Organizations can spend, including the funds received under the
one-time lockbox disbursement of ZIP 271 [^zip-0271] and any assets acquired
with or derived from them.

The Claims Reserve MUST NOT be funded from ZCG funds, from the Key-Holder
Organizations' own funds, or from Stranded Funds.

The Claims Reserve SHALL take priority over any grant approved in a
coinholder-amount voting round that closes after the Adoption Vote.

### Shortfall at the Adoption Date

If, at the Adoption Date, the Coinholder-Controlled Fund assets that the
Key-Holder Organizations can spend total less than 8,000 ZEC after payments
for previously approved grants that are already due, then:

* the Key-Holder Organizations MUST transfer all such assets to the Reserve
  Account within 14 days of the Adoption Date; and
* any later Coinholder-Controlled Fund assets that come under the control of
  the Key-Holder Organizations, for example by a future ZIP that defines a
  disbursement mechanism for funds accruing in the in-protocol lockbox
  [^zip-1015-lockbox], MUST first be used to bring the Reserve Account up to
  8,000 ZEC before being used for any other purpose.

The Key-Holder Organizations MUST publish the amount of any shortfall within
14 days of the Adoption Date, and MUST publish each later top-up.

## Reserve Account

The Reserve Account MUST be a separate address, or set of addresses, used only
for the Claims Reserve. The Claims Reserve MUST NOT be commingled with any
other funds, including other Coinholder-Controlled Fund assets.

The Reserve Account MUST be controlled by all of the Key-Holder Organizations
under a spending threshold at least as strict as that of the multisig used for
the rest of the Coinholder-Controlled Fund (2-of-3 at the time of writing
[^zip-0271]). A threshold signature scheme such as FROST [^zip-0312] MAY be
used. If the membership of the Key-Holder Organizations changes, control of
the Reserve Account MUST be transferred to the new Key-Holder Organizations in
the same way as the rest of the Coinholder-Controlled Fund.

The Reserve Account MAY be a transparent address or a shielded address. If it
is a shielded address, the Key-Holder Organizations MUST publish a full viewing
key or incoming and outgoing viewing keys sufficient for anyone to verify the
balance of the Reserve Account and every transaction to and from it.

The Key-Holder Organizations MUST publish the Reserve Account address (and any
viewing keys) on the Zcash Community Forum within 7 days of the Adoption Date,
and MUST publish a signed statement of the Reserve Account balance at least
once per quarter.

The Claims Reserve MUST be held as ZEC. It MUST NOT be invested, lent, staked,
pledged as collateral, or exchanged for any other asset.

## Permitted uses

The Claims Reserve MUST be used only to pay claims by Deprecated-Pool Holders
that are approved under the Claims Process ZIP.

In particular, funds in the Reserve Account:

* MUST NOT be disbursed as grants, whether or not a coinholder-amount voting
  round approves the grant;
* MUST NOT be used to pay the Key-Holder Organizations' administration costs,
  unless and to the extent that the Claims Process ZIP expressly allows it; and
* MUST NOT be returned to the general Coinholder-Controlled Fund, except as
  provided in [Release of the reserve](#release-of-the-reserve).

The Key-Holder Organizations MAY move funds between Reserve Account addresses
for security reasons, such as key rotation or a migration required by a network
upgrade, and MUST publicly report any such move within 7 days.

## Claims process (TBD)

The claims process is to be specified in a separate Claims Process ZIP, which
MUST itself be approved in a coinholder-amount voting round before any claim is
paid. Until a Claims Process ZIP is Active, the Key-Holder Organizations MUST
NOT pay any claim from the Claims Reserve.

The Claims Process ZIP is expected to address at least the following. Each
item below is a placeholder.

1. Eligibility: [TBD: which Deprecated Pools, and which Stranded Funds, are
   eligible. Whether funds that entered a pool after a public deprecation
   announcement are treated differently. Whether there is a minimum claim.]
2. Proof of holding: [TBD: how a claimant proves that they held spending
   authority for specific Stranded Funds at the relevant activation height,
   and that those funds were not spent before it, without revealing more than
   necessary. For Sprout, this might use a zero-knowledge proof of knowledge
   of a spending key for an unspent note in the Sprout note commitment tree at
   the NU7 activation height, verified off-chain.]
3. Preventing double recovery: [TBD: how to stop the same Stranded Funds
   being claimed twice, for example by publishing a nullifier or other unique
   tag for each claimed note, and what happens if spending from that pool is
   later re-enabled.]
4. Successors and custodians: [TBD: how estates, heirs, custodians,
   exchanges, and holders of funds on behalf of others establish their right to
   claim, and how conflicting claims are resolved.]
5. Claim window: [TBD: when claims open and close, and how the window is
   announced.]
6. Payout formula: [TBD: whether claims are paid 1 ZEC per ZEC of Stranded
   Funds, or pro rata if total valid claims exceed the Claims Reserve, and
   whether claims are paid in one batch at the end of the window or as they
   are approved.]
7. Legal compliance: [TBD: what, if any, identity or sanctions screening
   the Key-Holder Organizations need to perform, and how to keep it to the
   minimum required by law.]
8. Privacy: [TBD: how claimant privacy is protected, including payment to
   shielded addresses and limits on what the Key-Holder Organizations publish
   about claimants.]
9. Disputes: [TBD: how a claimant can challenge a rejected claim, and who
   decides.]
10. Administration costs: [TBD: whether reasonable costs of running the
    claims process may be paid from the Claims Reserve, and any cap.]
11. Unclaimed funds: [TBD: what happens to any part of the Claims Reserve
    that remains after the claim window closes; see also
    [Release of the reserve](#release-of-the-reserve).]
12. Reporting: [TBD: what aggregate statistics the Key-Holder
    Organizations publish about claims received, approved, rejected, and paid.]

## Release of the reserve

Any part of the Claims Reserve MAY be returned to the general
Coinholder-Controlled Fund only if both of the following hold:

* a ZIP (which MAY be the Claims Process ZIP) specifies the release; and
* that ZIP, or the specific release, is approved in a coinholder-amount voting
  round.

If, after the Adoption Date, a network upgrade re-enables spending of all
Stranded Funds in every Deprecated Pool, the Key-Holder Organizations SHOULD
hold a coinholder-amount voting round on whether to release the Claims
Reserve.

If the Coinholder-Controlled Fund ceases to exist, or a ZIP replaces the
Key-Holder Organizations' role, the Claims Reserve and the obligations of this
ZIP MUST be transferred to whichever organizations take over custody of the
Coinholder-Controlled Fund.

## Changes to ZIP 1016

In the section "Requirements on use of the Coinholder-Controlled Fund" of ZIP
1016, after:

> In particular, all requirements on the use of Deferred Dev Fund Lockbox funds
> in ZIP 1015 MUST be followed for the Coinholder-Controlled Fund.

add:

> As an exception, the Key-Holder Organizations MUST set aside and administer
> a Deprecated-Pool Claims Reserve as specified in ZIP [this ZIP]. Funds in that
> reserve are not available for grants and MUST be used only as that ZIP
> specifies.

## Legal agreements

ZIP 1016 requires the Key-Holder Organizations to be bound by a legal agreement
to use the Coinholder-Controlled Fund only according to ZIP 1016
[^zip-1016-use]. The Key-Holder Organizations SHALL amend that agreement, or
enter into a new one, to bind themselves to the requirements of this ZIP, and
SHALL publish a statement that they have done so within 30 days of the
Adoption Date.

## Security precautions

The security precautions in ZIP 1016 [^zip-1016-security] apply to the Reserve
Account. Any theft or loss of funds from the Reserve Account, or any loss or
compromise of its key material, MUST be reported to the Zcash community as
promptly as possible after applying necessary mitigations.

## Testnet-specific considerations

This ZIP does not require a Testnet reserve. The Key-Holder Organizations MAY
rehearse the transfer to the Reserve Account, and any claims process, on
Testnet.


# Rationale

## Why a fixed amount of ZEC

The intended size of the reserve is about US$10 million. Specifying the reserve in ZEC
rather than USD avoids any need for the Key-Holder Organizations to trade ZEC,
removes the need for a price oracle, and lets coinholders see exactly what
they are voting to set aside. It also matches the unit of the losses: Stranded
Funds are denominated in ZEC, so if the claims process pays 1 ZEC per ZEC
claimed, the reserve's purchasing power moves with the claims.

## Why the reserve does not cover all Sprout funds

The reserve covers about 36% of the roughly 22,300 ZEC that remained in Sprout
as of October 2026 [^zip-0218-pools]. Much of that balance is likely to belong
to lost keys and will never be claimed. A reserve sized to the whole balance
would tie up most of the Coinholder-Controlled Fund for funds that are
unlikely to be claimed. If valid claims exceed the reserve, the Claims Process
ZIP can pay them pro rata, and coinholders can vote to add to the reserve.

## Why set aside at the time of the vote

Designing a claims process for Sprout is a substantial piece of work (it may
need a new zero-knowledge proof of historical note ownership). If the reserve
were only created once that work was done, the Coinholder-Controlled Fund might
already have been spent on grants. Encumbering the funds when the vote closes
removes that risk and gives holders an assurance in the meantime.

## Why a separate account

A separate account makes it publicly verifiable that the reserve exists and has
not been spent, and prevents it from being drawn on by accident when grant
payments are made.

## Why "deprecated pools" and not only Sprout

Sprout is the first pool to be stranded, but ZIP 2005 shows that Sapling and
Orchard may follow [^zip-2005-effects]. Defining Deprecated Pools generally
lets the same reserve and claims framework apply without a new ZIP each time.
The Claims Process ZIP can still restrict eligibility to particular pools, and
coinholders can vote to add to the reserve when another pool is deprecated.

## Why the claims process is left TBD

The hard questions (how to prove historical ownership privately, how to handle
custodians and estates, what legal screening is needed) need input from
cryptographers, wallet developers, and the Key-Holder Organizations' counsel.
Separating them lets coinholders decide now whether a reserve should exist at
all, without waiting for that work.


# Security Considerations

The Claims Reserve adds a pool of funds that attackers may target, both by
attacking the Key-Holder Organizations' keys and by submitting fraudulent
claims. The custody requirements in [Reserve Account](#reserve-account) address
the first. The Claims Process ZIP will need to address the second, including claims
based on forged or replayed proofs, and claims made by someone who obtained a
Sprout spending key without being its lawful holder.

If a cryptographic break makes it possible to forge proofs of Sprout note
ownership, claims based on such proofs could drain the reserve. The Claims
Process ZIP will need to take this into account when choosing a proof system.


# Assumptions and Open Questions

* Funding source (assumption): this draft assumes the reserve comes from
  Coinholder-Controlled Fund assets held by the Key-Holder Organizations (in
  practice, the remainder of the 78,750 ZEC one-time lockbox disbursement
  [^zip-0271]), and not from the 12% stream that accrues to the in-protocol
  lockbox, for which no spend path is defined. If too little of the one-time
  disbursement remains, the shortfall rules apply.
* Authority: ZIP 1016 ties use of the Coinholder-Controlled Fund to the
  ZIP 1015 lockbox purpose of "funding grants to ecosystem participants"
  [^zip-1015-lockbox]. This draft adds an express exception, but whether the
  Key-Holder Organizations' legal agreements, charitable status, or other
  obligations allow them to make non-grant payments needs review by their
  counsel.
* Binding effect: ZIP 1016 only recommends that Key-Holder Organizations sign
  disbursements for approved grants, while this draft makes the set-aside
  mandatory.
  It is not clear what remedy exists if a Key-Holder Organization declines.
* Amount: Is 8,000 ZEC the right amount, and should the reserve
  automatically grow when another pool becomes a Deprecated Pool?
* Other stranded value: Should the definition extend to funds stranded for
  other reasons, such as version 4 transactions that were signed but not mined
  before NU7 activation [^zip-0259]? This draft does not include them, because
  the underlying funds remain spendable.
* Time limit: Should the reserve be released automatically if no Claims
  Process ZIP is Active within some period (for example, three years after the
  Adoption Date)?


# References

[^BCP14]: [Information on BCP 14, "RFC 2119: Key words for use in RFCs to Indicate Requirement Levels" and "RFC 8174: Ambiguity of Uppercase vs Lowercase in RFC 2119 Key Words"](https://www.rfc-editor.org/info/bcp14)

[^protocol-networks]: [Zcash Protocol Specification, Version 2025.6.0 [NU6.1 proposal]. Section 3.12: Mainnet and Testnet](protocol/protocol.pdf#networks)

[^zip-0209]: [ZIP 209: Prohibit Out-of-Range Chain Value Pool Balances](zip-0209.rst)

[^zip-0218-pools]: [ZIP 218: 25-second Block Target Spacing, shielded pool balances as of 21 October 2026](zip-0218.md)

[^zip-0259]: [ZIP 259: Deployment of the NU7 Network Upgrade](zip-0259.md)

[^zip-0271]: [ZIP 271: Dev Fund Extension and One-Time Disbursement](zip-0271.md)

[^zip-0312]: [ZIP 312: FROST for Spend Authorization Multisignatures](zip-0312.rst)

[^zip-1015-lockbox]: [ZIP 1015: Block Subsidy Allocation for Non-Direct Development Funding, Lockbox](zip-1015.rst#lockbox)

[^zip-1016]: [ZIP 1016: Community and Coinholder Funding Model](zip-1016.md)

[^zip-1016-use]: [ZIP 1016: Community and Coinholder Funding Model, Requirements on use of the Coinholder-Controlled Fund](zip-1016.md#requirements-on-use-of-the-coinholder-controlled-fund)

[^zip-1016-disbursement]: [ZIP 1016: Community and Coinholder Funding Model, Disbursement process](zip-1016.md#disbursement-process)

[^zip-1016-security]: [ZIP 1016: Community and Coinholder Funding Model, Security precautions](zip-1016.md#security-precautions)

[^zip-2003]: [ZIP 2003: Disallow version 4 transactions](zip-2003.rst)

[^zip-2005-effects]: [ZIP 2005: Ironwood Quantum Recoverability, Effects of discrete-logarithm-breaking attacks after the switch to the Recovery Protocol](zip-2005.md)

[^draft-mcgee-keyholders]: [Draft ZIP: Update to ZIP 1016 & ZIP 271: Key-Holder Organizations](draft-mcgee-keyholders-organizations.md)

[^coingecko-zec]: [CoinGecko: Zcash (ZEC) price, accessed 2026-11-08](https://www.coingecko.com/en/coins/zcash)
