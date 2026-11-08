    ZIP: Unassigned
    Title: Update to ZIP 1016: Key-Holder Organization Management Fee
    Owners: Emerson <TBD>
    Status: Draft
    Category: Process
    Created: 2026-11-08
    License: MIT
    Discussions-To: <URL TBD>
    Updates: 1016


# Terminology

The key words "MUST", "MUST NOT", "SHALL", "SHALL NOT", "SHOULD", and "MAY" in
this document are to be interpreted as described in BCP 14 [^BCP14] when, and
only when, they appear in all capitals.

The terms "Mainnet" and "Testnet" in this document are to be interpreted as
defined in the Zcash protocol specification [^protocol-networks].

The terms "Coinholder-Controlled Fund" and "Key-Holder Organizations" in this
document are to be interpreted as described in ZIP 1016 [^zip-1016], as
amended by any ZIP that updates the membership of the Key-Holder Organizations
(see for example [^draft-mcgee-keyholders]).

The term "Deferred Dev Fund Lockbox" is to be interpreted as defined in
ZIP 1015 [^zip-1015].

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

: The date on which the Key-Holder Organizations publish the certified result
  of an Adoption Vote that approves this ZIP.

Fee Quarter

: A calendar quarter (January to March, April to June, July to September, or
  October to December, in UTC). The first Fee Quarter is the one that begins
  after the Adoption Date.

Managed Assets

: For a Fee Quarter, the total ZEC held, at the last block mined on or before
  23:59:59 UTC on the final day of that Fee Quarter, at (a) the ZIP 271
  multisig address that received the one-time lockbox disbursement
  [^zip-0271-disbursement], and any address to which those funds are moved by
  the Key-Holder Organizations; and (b) any other address controlled jointly
  by the Key-Holder Organizations that holds funds of the
  Coinholder-Controlled Fund, including funds received by a future
  disbursement from the Deferred Dev Fund Lockbox.

  Managed Assets do not include funds that are still held in the Deferred Dev
  Fund Lockbox by the consensus rules, funds that a coinholder-amount voting
  round has approved for payment to a grant recipient and that the Key-Holder
  Organizations have set aside for that payment, or funds that another ZIP
  places in a separate reserve with its own rules.

Security Costs

: Costs a Key-Holder Organization actually incurs, during a Fee Quarter,
  because it is a Key-Holder Organization, in the categories listed in
  [Security reimbursement](#security-reimbursement).

Reference Price

: For a date, the volume-weighted average USD price of ZEC on that date as
  published by a price source named in the Key-Holder Organizations' fee
  policy, or, if no such source has been named, the daily closing USD price
  published by CoinGecko.


# Abstract

This ZIP sets a management fee for the Key-Holder Organizations that
administer the Coinholder-Controlled Fund under ZIP 1016. Each Key-Holder
Organization receives an equal share of a base fee of 0.5% per year of the
Managed Assets, paid quarterly from the Fund. In addition, each Key-Holder
Organization may be reimbursed from the Fund for documented Security Costs,
up to a further 0.5% per year of the Managed Assets in total. All fees and
reimbursements are reported publicly each quarter and reviewed once a year
by an independent accountant.

The fee takes effect only if coinholders approve this ZIP in a
coinholder-amount voting round.

Because security spending can reveal how people protect themselves and their
families, public reports give category totals only, and the detail stays with
the independent accountant.


# Motivation

ZIP 1016 asks the Key-Holder Organizations to hold keys to the
Coinholder-Controlled Fund, run coinholder votes, assess grants for legal
problems, decide on vetoes, sign payouts, and "take appropriate precautions to
safeguard funds from theft or accidental loss" [^zip-1016-security]. It does
not say who pays for any of this. Today each Key-Holder Organization pays for
its own share of the work from its own budget, which was raised for other
purposes.

The amounts are large. At NU6.1 the Key-Holder Organizations received 78,750
ZEC from the Deferred Dev Fund Lockbox [^zip-0271-disbursement], about 99
million USD at 1,262 USD per ZEC (CoinGecko, 2026-11-08), of which grant
rounds have since paid out part (about 8.39 million USD in Q3 2026 alone
[^cryptonews-q3]). The lockbox stream continues until Mainnet height 6132390
[^zip-0214-rev3], adding about 216 ZEC a day on top of the roughly 74,400 ZEC
that built up before NU7. In total, roughly 315,000 ZEC (about 400 million
USD) may pass through Key-Holder Organization custody.

Holding keys to funds of this size makes the people involved targets.
Kidnapping and home-invasion "wrench attacks" against people known to control
cryptocurrency have become more common. Some people associated with Key-Holder
Organizations have already hired personal security at conferences. Protection
of this kind, together with crime insurance, secure key storage, and the legal
work that ZIP 1016 requires, is a real and continuing cost. As rough planning
estimates, not quotes: event close protection costs about 1,500 to 3,000 USD
per agent per day; full-time executive protection about 250,000 USD to more
than 1 million USD per person per year; crime insurance on digital assets,
where available, about 0.5% to 2% of the insured amount per year; and key
management, audits, and legal work about 150,000 to 450,000 USD per
organization per year.

If these costs are not paid, Key-Holder Organizations may cut corners on
security, or may stop serving. Either outcome puts the Fund and the people at
risk. If each Key-Holder Organization pays for these costs out of its own
budget, the work is funded in a way coinholders cannot see or control.

A fixed, published fee, approved by coinholders, gives the Key-Holder
Organizations a predictable amount for routine administration, reimburses
security spending only against evidence, and lets coinholders see and change
what the Fund pays.


# Privacy Implications

The quarterly report and the annual review deal with sensitive information
about people's security. This ZIP limits public reporting to totals by
category and keeps detail with an independent accountant under
confidentiality. Fee payments are made from the transparent multisig and are
visible on chain, as all Fund payments already are.


# Requirements

* The fee is set by a ZIP and approved by coinholders, not chosen by the
  Key-Holder Organizations themselves.
* The fee is simple to compute from public chain data.
* The fee scales with the amount the Key-Holder Organizations are responsible
  for.
* Security Costs can be paid for without publishing details that would help an
  attacker.
* The total paid out each year has a hard ceiling.
* Every payment is reported publicly and reviewed independently.


# Non-requirements

* This ZIP does not change the Key-Holder Organizations, the voting threshold,
  the veto process, or any other part of ZIP 1016 except as listed in
  [Changes to ZIP 1016](#changes-to-zip-1016).
* This ZIP does not change any consensus rule.
* This ZIP does not set compensation for the ZCG Committee or Financial Privacy
  Foundation, which ZIP 1015 already covers.
* This ZIP does not say how a Key-Holder Organization pays its own staff or
  contractors from the fee it receives.


# Specification

## Adoption

The Key-Holder Organizations SHALL hold an Adoption Vote on this ZIP in the
first coinholder-amount voting round that opens at least 30 days after this
ZIP reaches Proposed status.

The question put to coinholders SHALL be whether to adopt this ZIP as written,
including the fee rates in [Base fee](#base-fee) and
[Security reimbursement](#security-reimbursement).

This ZIP is adopted if the Adoption Vote meets the same participation
threshold and majority that ZIP 1016 requires for a grant proposal
[^zip-1016-disbursement].

A Key-Holder Organization SHALL NOT exercise a veto under ZIP 1016 against
this ZIP or against the Adoption Vote, since the Key-Holder Organizations are
the recipients of the fee. A Key-Holder Organization MAY declare that it will
not accept the fee, in which case its share is not paid and stays in the
Fund.

## Base fee

For each Fee Quarter, the base fee is 0.125% (one quarter of 0.5%) of the
Managed Assets for that Fee Quarter.

The base fee SHALL be split equally among the Key-Holder Organizations that
held that role on the last day of the Fee Quarter and that have not declined
the fee. If a Key-Holder Organization was replaced during the Fee Quarter, the
outgoing and incoming organizations share that seat's portion in proportion to
the number of days each held the role.

The base fee is computed and paid in ZEC. No price conversion is involved.

The base fee is meant to cover routine administration: running coinholder
votes, reviewing grants for legal and reporting problems, signing payouts, and
preparing the reports this ZIP and ZIP 1016 require.

## Security reimbursement

In addition to the base fee, a Key-Holder Organization MAY claim reimbursement
from the Fund for Security Costs in these categories:

1. Personal protection for its key-holders, directors, officers, and other
   people whose role in the Fund is publicly known, and for members of their
   households, including close protection at events and travel security.
2. Physical security of homes and offices of the people in category 1.
3. Insurance that covers theft or loss of Fund assets, or kidnap, ransom, and
   extortion risk for the people in category 1.
4. Secure key storage and key management, including hardware security
   modules, secure facilities, key ceremonies, and security audits of the
   Key-Holder Organization's signing setup.
5. Legal and compliance work needed to meet the Key-Holder Organization's
   obligations under ZIP 1016 and its legal agreement for the Fund.

Security Costs MUST NOT include any cost that the Key-Holder Organization has
already been paid for from another source, including another grant or the
base fee.

For each Fee Quarter, the total reimbursement paid to all Key-Holder
Organizations together MUST NOT exceed 0.125% (one quarter of 0.5%) of the
Managed Assets for that Fee Quarter. If the claims for a Fee Quarter are
larger than this cap, each claim is reduced in the same proportion. The amount
by which a claim was cut back does not carry over to later Fee Quarters.

Claims SHALL be made in USD, or in the currency in which the cost was
incurred, and converted to ZEC at the Reference Price on the last day of the
Fee Quarter.

## Payment

Fees and reimbursements for a Fee Quarter SHALL be paid no earlier than 15
days and no later than 45 days after the end of that Fee Quarter, after the
report for that Fee Quarter has been published.

Payments SHALL be made from the Coinholder-Controlled Fund by the normal
multisig signing process. Each payment transaction SHALL be identified in the
quarterly report.

A Key-Holder Organization SHALL NOT receive a fee or reimbursement for a Fee
Quarter in which it has failed to report a theft, loss, or key compromise as
ZIP 1016 requires [^zip-1016-security], or for any Fee Quarter that begins
before it has corrected that failure.

## Quarterly report

Before any payment for a Fee Quarter, the Key-Holder Organizations SHALL
jointly publish a report on the Zcash Community Forum that states:

* the Managed Assets for the Fee Quarter, and the addresses and block height
  used to compute it;
* the base fee and each Key-Holder Organization's share;
* for each Key-Holder Organization, the total Security Costs claimed in each
  of the five categories, the amount after any reduction for the cap, and the
  Reference Price used;
* any Key-Holder Organization that declined the fee or was not eligible; and
* the transaction ids of the payments, added once they are made.

The report SHALL give Security Costs only as totals by category. It SHALL NOT
name security providers, insurers, or protected people, or give dates,
places, or other details that would help someone plan an attack.

## Annual review

For each calendar year in which any fee or reimbursement is paid, the
Key-Holder Organizations SHALL engage an independent accountant who is not
an employee or officer of any Key-Holder Organization. The accountant SHALL
review the receipts and records behind every Security Costs claim, and SHALL
publish a short statement on the Zcash Community Forum, by March 31 of the
following year, saying whether the claims were supported and fell within the
categories in this ZIP.

The accountant MAY see full details of Security Costs under a confidentiality
agreement. The accountant's public statement SHALL follow the same limits as
the quarterly report.

If the accountant finds that any amount was paid without support or outside
the permitted categories, the Key-Holder Organization that received it SHALL
return that amount, in ZEC, to the Fund within 60 days.

The cost of the annual review MAY be paid from the Fund and counts toward the
reimbursement cap for the Fee Quarter in which it is paid.

## Changing the fee

The rates in this ZIP can be changed only by a later ZIP that is approved by
a coinholder-amount voting round under the same rules as the Adoption Vote.
The Key-Holder Organizations SHALL NOT raise the rates, add categories, or
change how Managed Assets are measured by any other means.

The Key-Holder Organizations MAY lower or waive any part of the fee for any
Fee Quarter by publishing a joint notice before the end of that Fee Quarter.

## End of the fee

No fee or reimbursement accrues for any period after the Coinholder-Controlled
Fund holds no Managed Assets, or after a ZIP that ends the
Coinholder-Controlled Fund takes effect, whichever comes first. Amounts already
accrued for earlier Fee Quarters remain payable.

## Changes to ZIP 1016

In the section "Requirements on use of the Coinholder-Controlled Fund", after
the first paragraph, the following paragraph is added:

> Notwithstanding the requirement that Coinholder-Controlled Fund be used for
> funding grants to ecosystem participants, the Key-Holder Organizations MAY
> pay from the Coinholder-Controlled Fund the management fee and security
> reimbursements specified in ZIP XXX, and no other fee for their
> administration of the Fund.

In the section "Security precautions", the following paragraph is added at the
end:

> The costs of these precautions MAY be reimbursed as specified in ZIP XXX.

## Legal agreements

ZIP 1016 binds the Key-Holder Organizations by legal agreement to use the Fund
only as that ZIP specifies [^zip-1016-requirements]. Before the first payment
under this ZIP, the Key-Holder Organizations SHALL amend that agreement, or
enter into a new one, so that it allows the fee and reimbursements described
here and requires return of any amount that the annual review finds was paid
improperly.

## Testnet-specific considerations

The fee computation and quarterly report SHOULD be rehearsed on Testnet, using
the Testnet ZIP 271 disbursement address, before the first Mainnet payment. No
fee is paid on Testnet.


# Rationale

## Why a fee at all

The Key-Holder Organizations took on this role as a service, but the role has
grown into the custody of a fund worth tens of millions of USD, with personal
risk to the people involved. Leaving it unpaid means coinholders depend on
each Key-Holder Organization's goodwill and outside budget, and have no view of
what is spent on keeping the Fund safe. A small published fee is cheaper than
a single theft.

## Why a percentage of assets

The risk and the work both grow with the size of the Fund. A percentage
follows the Fund up and down without a new ZIP each time the balance or the
price changes. It is computed in ZEC from chain data, so it does not need a
price feed.

The base rate of 0.5% per year is at or below what regulated digital-asset
custodians commonly charge institutional clients, and well below the 1% to 2%
typical of investment funds. At about 70,000 ZEC of Managed Assets it comes to
about 350 ZEC per year (about 440,000 USD at today's price), or about 117 ZEC
per Key-Holder Organization.

## Why security costs are separate

Security needs are uneven. One organization may have staff who travel often
and are well known, while another may not. A single flat fee would either
overpay some or underpay others. Paying security against receipts, under a
cap, puts the money where the risk is. It also means coinholders can see that
security spending is real.

The cap of a further 0.5% per year limits the worst case to 1% per year in
total. At about 70,000 ZEC that is about 700 ZEC per year (about 880,000 USD),
enough for event protection, insurance, and key management for three
organizations, but not enough for unlimited full-time protection.

## Why only totals are reported

Publishing who is protected, by whom, and when would tell an attacker exactly
what to plan around. Reporting totals by category, with the detail checked by
an independent accountant, keeps the spending accountable without making
anyone less safe.

## Why lockbox funds are not counted

Funds still in the Deferred Dev Fund Lockbox are protected by consensus rules
and are not in Key-Holder Organization custody. They become Managed Assets
only when a disbursement moves them to an address the Key-Holder
Organizations control.

## Why no fee on approved payouts

Funds that coinholders have approved for a grant and that are waiting to be
paid are excluded, so that the Key-Holder Organizations gain nothing by
delaying payouts. The fee is also not based on the amount paid out, so that
it does not reward approving or blocking grants.

## Why Key-Holder Organizations cannot veto this ZIP

The veto in ZIP 1016 exists to protect Zcash users and the Key-Holder
Organizations' legal position. It is not meant for deciding on their own pay.
A Key-Holder Organization that does not want the fee can decline it.


# Security Considerations

Paying for security is the point of this ZIP. The main new risk is that fee
transactions add to the number of times the multisig keys are used. Making one
payment transaction per Fee Quarter, covering all Key-Holder Organizations,
keeps this small.

A second risk is that publishing the fee draws more attention to the people
who hold keys. Their role is already public under ZIP 1016 and the McGee
Key-Holder Organizations draft [^draft-mcgee-keyholders], so the added
exposure is small, and the fee pays for protection against it.


# Assumptions and Open Questions

* The fee structure (0.5% per year base plus up to 0.5% per year of security
  reimbursement) is the draft author's starting point. Alternatives considered
  were a flat 1% per year with no reimbursement, a flat 250 ZEC per year per
  Key-Holder Organization, and reimbursement only, capped at 1% per year.
* The remaining balance of the ZIP 271 multisig has not been confirmed from
  chain data. The figure of about 70,000 ZEC used in the Rationale is an
  estimate.
* The security cost figures in the Motivation are rough industry estimates
  and should be checked with providers before the Adoption Vote.
* ZIP 1015 says lockbox funds are for "funding grants to ecosystem
  participants" [^zip-1015-lockbox]. This ZIP adds an explicit exception to
  ZIP 1016, but each Key-Holder Organization's counsel should confirm that the
  exception is consistent with its legal agreement and, where relevant, its
  charitable status.
* Should a Key-Holder Organization that is a charity or association be allowed
  to pass the base fee to its general budget, or should it be held for Fund
  work only?
* Should the reimbursement cap be per Key-Holder Organization instead of
  shared?


# References

[^BCP14]: [Information on BCP 14, "RFC 2119: Key words for use in RFCs to Indicate Requirement Levels" and "RFC 8174: Ambiguity of Uppercase vs Lowercase in RFC 2119 Key Words"](https://www.rfc-editor.org/info/bcp14)

[^protocol-networks]: [Zcash Protocol Specification, Version 2026.8.0 [NU6.3]. Section 3.12: Mainnet and Testnet](protocol/protocol.pdf#networks)

[^zip-0214-rev3]: [ZIP 214: Consensus rules for a Zcash Development Fund, Revision 3](zip-0214.rst)

[^zip-0271-disbursement]: [ZIP 271: Deferred Dev Fund Lockbox Disbursement, One-time lockbox disbursement](zip-0271.md)

[^zip-1015]: [ZIP 1015: Block Subsidy Allocation for Non-Direct Development Funding](zip-1015.rst)

[^zip-1015-lockbox]: [ZIP 1015: Block Subsidy Allocation for Non-Direct Development Funding, Lockbox](zip-1015.rst#lockbox)

[^zip-1016]: [ZIP 1016: Community and Coinholder Funding Model](zip-1016.md)

[^zip-1016-requirements]: [ZIP 1016: Community and Coinholder Funding Model, Requirements on use of the Coinholder-Controlled Fund](zip-1016.md#requirements-on-use-of-the-coinholder-controlled-fund)

[^zip-1016-disbursement]: [ZIP 1016: Community and Coinholder Funding Model, Disbursement process](zip-1016.md#disbursement-process)

[^zip-1016-security]: [ZIP 1016: Community and Coinholder Funding Model, Security precautions](zip-1016.md#security-precautions)

[^draft-mcgee-keyholders]: [Draft ZIP: Update to ZIP 1016 & ZIP 271: Key-Holder Organizations](draft-mcgee-keyholders-organizations.md)

[^cryptonews-q3]: [crypto.news, 1 October 2026: Zcash price holds $1,400 as holders approve $8.4M grants](https://crypto.news/zcash-price-holds-1400-as-holders-approve-8-4m-grants/)
