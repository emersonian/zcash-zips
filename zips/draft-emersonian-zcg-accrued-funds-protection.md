    ZIP: Unassigned
    Title: Protection and Treasury Management of Accrued Zcash Community Grants Funds
    Owners: Emerson <TBD>
    Status: Draft
    Category: Process
    Created: 2026-11-08
    License: MIT
    Discussions-To: <URL TBD>
    Updates: 1015, 1016


# Terminology

The key words "MUST", "MUST NOT", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT",
and "MAY" in this document are to be interpreted as described in BCP 14
[^BCP14] when, and only when, they appear in all capitals.

The terms "Zcash Community Grants" (or "ZCG"), "ZCG Committee", "Financial
Privacy Foundation" (or "FPF"), "Autonomous Entities", "Zcash Community
Advisory Panel" (or "ZCAP"), and "Discretionary Budget" in this document are to
be interpreted as defined or used in ZIP 1015 [^zip-1015]. In this ZIP the ZCG
Committee is also called the grants committee, to distinguish it from the
Treasury Committee.

The terms "Coinholder-Controlled Fund" and "Key-Holder Organizations" in this
document are to be interpreted as described in ZIP 1016 [^zip-1016].

The terms "Mainnet" and "Testnet" in this document are to be interpreted as
defined in the Zcash protocol specification [^protocol-networks].

"ZEC" refers to the native currency of Zcash on Mainnet.

The terms below are to be interpreted as follows:

Coinholder-amount voting round

: A coinholder vote held under ZIP 1016 [^zip-1016-disbursement], in which each
  ballot is weighted by the amount of ZEC that the voter proves control of,
  conducted under the rules for such votes in effect at the time the vote is
  held.

ZCG Funding Stream

: Any funding stream whose recipient is FPF, or a successor administrator, for
  the use of Zcash Community Grants. At the time of writing these are
  `FS_FPF_ZCG` [^zip-1015-funding-streams] and `FS_FPF_ZCG_H3` [^zip-0214]
  [^zip-1016-zcg]. The term includes any later funding stream defined for the
  same purpose, under any name.

Accrued ZCG Funds

: All of the following:

  1. each amount paid to a recipient address of a ZCG Funding Stream, from the
     block in which the payment is mined;
  2. each amount donated or otherwise contributed to FPF, or a successor
     administrator, for the use of Zcash Community Grants, from the time it is
     received;
  3. each amount returned to the ZCG program, such as an unspent grant
     tranche, a recovered grant payment, or an unspent part of the
     Discretionary Budget; and
  4. all assets that any of the above is converted into or earns, including
     fiat currency, stablecoins, other digital assets, deposits, interest,
     yield, and the proceeds of any hedging position.

  Funds remain Accrued ZCG Funds for as long as they are held, in whatever
  account, wallet, custodian, or asset they are held. They cease to be Accrued
  ZCG Funds only when paid out for a Permitted Use.

Reference Text

: The section "Zcash Community Grants (ZCG)" of ZIP 1015 [^zip-1015-zcg],
  together with any amendment to that section that is in a ZIP with status
  Active or Final on the Activation Date, as that text reads on the Activation
  Date.

Permitted Use

: A use of funds described in
  [Permitted uses of Accrued ZCG Funds](#permitted-uses-of-accrued-zcg-funds).

Controlling Organization

: Any organization or person that holds, administers, has signing authority
  over, acts as custodian of, or can direct the movement of any Accrued ZCG
  Funds. This includes FPF (including its directors, supervisor, and members),
  the ZCG Committee and its members, the Treasury Committee and its members, any
  successor administrator of the ZCG program, and any custodian, trustee,
  signer, or service provider acting for any of them. It also includes the Zcash
  Foundation, Electric Coin Company, Bootstrap Project, any Key-Holder
  Organization, or any other organization, at any time that it holds or controls
  Accrued ZCG Funds.

Taking

: Any action that causes Accrued ZCG Funds to leave the ZCG program other than
  by payment for a Permitted Use, or that makes them unusable for a Permitted
  Use.

Accrual Rate

: The share of the block subsidy, or of any other issuance defined by the
  consensus rules, that is paid to ZCG Funding Streams, together with the start
  and end heights of those streams.

Treasury Committee

: The ZCG Treasury Committee established under
  [ZCG Treasury Committee](#zcg-treasury-committee).

Treasury Decision

: A decision of a kind listed in
  [Treasury Decisions](#treasury-decisions).

Grant Decision

: A decision of a kind listed in [Grant Decisions](#grant-decisions).

Program Budget

: The budget for the ZCG program set by the Treasury Committee under
  [Program Budget](#program-budget).

Treasury Plan

: The ten-year budget, treasury policy, and hedging strategy described in
  [Treasury Plan](#treasury-plan).

Activation Date

: The date on which this ZIP becomes Active under ZIP 0 [^zip-0000].

Protection Date

: The later of the Activation Date and the date on which FPF publishes the
  legal commitment described in
  [Legal commitment by FPF](#legal-commitment-by-fpf).


# Abstract

This ZIP protects funds that have already accrued to Zcash Community Grants
(ZCG) and changes how ZCG manages them.

No ZIP, network upgrade, vote, or agreement may reduce, redirect, burn, or
otherwise take funds that have accrued to ZCG. FPF, the ZCG Committee, and any
other organization that holds or controls those funds may use them only for
grants and grant administration as defined in ZIP 1015. Transfers to the
Network Sustainability Mechanism, to unspendable addresses, to a lockbox, or
to the Coinholder-Controlled Fund are prohibited. A future ZIP may change only
the rate at which new funds accrue to ZCG, and only for future blocks.

ZCG is required to form a separate Treasury Committee of at least three people.
Only the Treasury Committee may buy, sell, or convert ZEC, hedge, or set
budgets. The ZCG grants committee makes grant decisions only, and no person may
sit on both committees. Until the Treasury Committee is formed, the grants
committee may not decide to buy or sell ZEC.

The Treasury Committee must publish a ten-year budget, a treasury plan, and a
strategy for hedging the risk of a fall in the price of ZEC by 31 March 2027.

The ZIP has privacy implications for the disclosure of treasury addresses,
trades, and the personal holdings of committee members, which are discussed
below.


# Motivation

## Proposals to take existing ZCG funds

In October 2026 several proposals were made to end or redirect ZCG funding. As
of late October 2026 these included a draft ZIP to end the ZCG funding stream
and redirect it to the Network Sustainability Mechanism (NSM) [^zips-pr-1414],
since closed; a draft ZIP to redirect the stream to a new lockbox and to have
the ZCG Committee send 50,000 ZEC of its existing balance to an unspendable
address, to be credited to the NSM at a later network upgrade
[^zips-pr-1428]; a draft ZIP to wind ZCG down [^zips-pr-1423]; and a ZCG
proposal on the Zcash Community Forum for a voluntary taper that would send
about 36,200 ZEC to the NSM [^forum-zcg-taper].

How much of the block subsidy should go to ZCG in future is a legitimate
question for the community, and this ZIP does not try to answer it. Some of
these proposals, however, would also take funds that were issued under rules
the community had already agreed, for a purpose those rules stated. This ZIP
treats that as a separate question, and answers it.

## Reasons to protect accrued funds

The funds were issued for a stated purpose. ZIP 1015 restricts the ZCG funds to
grants to parties independent of FPF, or to Autonomous Entities, plus related
administration, and requires FPF to hold them as a restricted fund donation.
Each block that paid the ZCG Funding Stream was produced, and each ZEC in it was
issued, on that basis.

Grantees and applicants rely on ZCG being able to pay. If its balance can be
taken by a later vote, every multi-year grant carries political risk, and
capable teams will either discount that risk or not apply.

There is legal exposure for FPF. Sending restricted funds to a purpose outside
the restriction, or to an address from which they can never be recovered, may
expose FPF's directors to claims under Cayman Islands law. In October 2026 FPF
said that its counsel had considered such a donation subject to "an
affirmative community vote in favor of the proposal and an accepted ZIP"
[^forum-fpf-reply]. Neither term is defined in any ZIP.

Taking validly issued funds from a disfavored recipient is, in governance
terms, close to freezing a disfavored user's coins. A clear rule against the
first makes it easier for the community to say credibly that it will not do
the second.

Finally, separating future funding from past funding lets the community debate
the Accrual Rate without that debate also being about money already committed.

## Reasons for a separate Treasury Committee

ZCG's balance is held largely in ZEC, while many grant obligations are
understood by grantees in US dollar terms. The ZCG Funding Stream is scheduled
to end at the third halving (Mainnet height 6132390 under ZIP 214 Revision 3
[^zip-0214], expected in late 2028), and could end sooner. A fall in the price
of ZEC can therefore reduce ZCG's ability to fund work by a large fraction
within months, with no change to any ZIP.

At the time of writing, the ZCG Committee both chooses grants and decides, with
FPF, how ZCG's funds are held and when ZEC is sold. These are different skills,
and combining them creates conflicts: a committee under pressure to fund a
popular grant may sell ZEC at a poor time, and a committee that decides when
ZCG sells ZEC has information that could be misused. ZCG also does not publish
a multi-year budget, a treasury policy, or a hedging policy.

If accrued funds are protected permanently, ZCG has a matching duty to manage
them well over a long period. A separate committee with its own members, a
published plan, and clear limits on what each committee may decide is intended
to meet that duty.


# Privacy Implications

Publishing treasury addresses, viewing keys, or detailed trade records lets
anyone link ZCG's holdings and movements over time. This is intended, since the
community needs to verify that Accrued ZCG Funds are not taken, but it can
also reveal ZCG's counterparties, the timing of its trades, and, through grant
payments, information about grantees. Publishing planned trades before they are
executed could also allow others to trade against ZCG.

Holding ZEC in shielded pools improves the privacy of ZCG and its grantees but
makes public verification depend on ZCG choosing to publish viewing keys or
attestations.

Disclosure of the personal ZEC holdings of Treasury Committee members, which
this ZIP requires in order to manage conflicts of interest, reveals sensitive
financial information about individuals.

The Specification addresses these trade-offs by allowing details of a trade to
be withheld until it has been executed, and by limiting personal disclosures
to what is needed to identify conflicts.


# Requirements

* Funds that have accrued to ZCG cannot be reduced, redirected, burned, or
  otherwise taken by any later ZIP, network upgrade, vote, or agreement.
* Accrued ZCG Funds can be used only for grants and grant administration as
  defined in ZIP 1015, and this binds every organization that holds or
  controls them.
* A future ZIP can still change the rate at which new funds accrue to ZCG,
  including to zero, for future blocks.
* The protection does not rely only on the ZIP process, which cannot prevent
  its own later amendment, and is also backed by a published legal commitment.
* Decisions about how ZCG's funds are held, converted, and hedged, and how much
  ZCG may spend, are made by a body separate from the body that chooses grants,
  with no overlapping members.
* While that separate body is being formed, the grants committee does not
  decide to buy or sell ZEC.
* A ten-year budget, treasury plan, and ZEC-depreciation hedging strategy are
  published by 31 March 2027 and kept current.
* Converting or hedging Accrued ZCG Funds is possible without being treated as
  a transfer out of the restricted fund.


# Non-requirements

* This ZIP does not set or change the Accrual Rate. In particular, it does not
  extend, reduce, or end the `FS_FPF_ZCG_H3` funding stream.
* This ZIP does not change how the ZCG Committee is selected, or FPF's ability
  to veto a decision that would violate Cayman Islands law under point 6 of the
  Reference Text.
* This ZIP does not cover the Coinholder-Controlled Fund, the in-protocol
  lockbox, or funds held by other organizations, except to the extent that they
  hold Accrued ZCG Funds.
* This ZIP does not prevent a Controlling Organization from complying with a
  court order, sanctions law, or other legal requirement that it cannot
  lawfully refuse.
* This ZIP does not decide whether the NSM, a new lockbox, or any other use of
  future issuance is desirable.


# Specification

## Adoption

The sections [ZCG Treasury Committee](#zcg-treasury-committee),
[Separation of grant and treasury decisions](#separation-of-grant-and-treasury-decisions),
[Interim restriction on the grants committee](#interim-restriction-on-the-grants-committee),
[Program Budget](#program-budget), and [Treasury Plan](#treasury-plan) take
effect on the Activation Date.

All other requirements of this ZIP take effect on the Protection Date.

Before the ZIP Editors change the status of this ZIP to Active, the community
SHOULD be consulted through both a coinholder-amount voting round, held by the
Key-Holder Organizations under the rules in effect at the time, and a poll of
ZCAP or its successor. The ZIP Editors SHOULD publish the results of both with
the status change.

Funds that accrued to ZCG before the Protection Date are Accrued ZCG Funds and
are protected by this ZIP in the same way as funds that accrue after it.

The ZIP Editors SHOULD record, when this ZIP becomes Active, the git commit of
the zcash/zips repository that contains the Reference Text.

## Protection of Accrued ZCG Funds

No ZIP, network upgrade, vote (including a coinholder-amount voting round or a
ZCAP poll), agreement, resolution, or other governance action, whether made
before or after the Protection Date, SHALL reduce, redirect, recapture, freeze,
burn, or otherwise take any Accrued ZCG Funds.

A provision of any ZIP that would require or authorize a Taking has no effect
to that extent, and no Controlling Organization SHALL act on it. This applies
however the Taking is described, including as a donation, contribution, return,
wind-down, taper, or rebalancing.

All Accrued ZCG Funds SHALL remain under the administration of the ZCG program,
to be used only for Permitted Uses.

## Permitted uses of Accrued ZCG Funds

Accrued ZCG Funds MUST be used only for:

1. Zcash Community Grants to external parties that are independent of FPF, or
   to Autonomous Entities operating under the FPF umbrella, as described in
   point 1 of the Reference Text and subject to points 2 to 7 of the Reference
   Text; and
2. expenses reasonably related to the administration of Zcash Community Grants,
   including the Discretionary Budget and committee compensation, as described
   in points 1, 8, 9, and 10 of the Reference Text, and the costs of the
   Treasury Committee and of treasury management under this ZIP.

Accrued ZCG Funds MUST NOT be used for any other purpose. In particular, they
MUST NOT be used for FPF's internal operations or for any direct expense
unrelated to the administration of Zcash Community Grants.

## Prohibited transfers

No Controlling Organization SHALL make, sign, approve, or permit any of the
following with Accrued ZCG Funds:

* a transfer to the Network Sustainability Mechanism, or to any address,
  output, or mechanism intended to be credited to it now or in future;
* a transfer to a provably unspendable address or an `OP_RETURN` output, or
  any other burn;
* a transfer to any in-protocol lockbox, to the Coinholder-Controlled Fund, or
  to any fund that is not administered for Permitted Uses;
* a distribution or refund to miners, coinholders, or any other class of
  persons;
* a transfer to FPF's general funds, the Zcash Foundation, Electric Coin
  Company, Bootstrap Project, or any other organization, other than as payment
  for a Permitted Use;
* a pledge of the funds as collateral or as a guarantee for any obligation that
  is not itself for a Permitted Use; or
* a loan of the funds to a Controlling Organization or to a related party of a
  Controlling Organization.

This applies whether the transfer is voluntary or mandatory, and whether or not
it is approved by the ZCG Committee, the Treasury Committee, FPF's board, a
coinholder-amount voting round, a ZCAP poll, or a ZIP.

## Treasury management

Converting Accrued ZCG Funds from one asset to another, moving them between
accounts, wallets, or custodians controlled by the ZCG program's administrator,
and opening or closing hedging positions, are not Takings and are not
prohibited transfers, provided that:

* the resulting assets remain Accrued ZCG Funds and are accounted for in ZCG's
  restricted fund;
* the action is a Treasury Decision made by the Treasury Committee, or is
  permitted by
  [Interim restriction on the grants committee](#interim-restriction-on-the-grants-committee);
* after the first Treasury Plan is published, the action is consistent with the
  Treasury Plan then in effect; and
* the action is reported in ZCG's next quarterly report.

Reasonable transaction, custody, and hedging costs are administration expenses
under item 2 of [Permitted uses of Accrued ZCG Funds](#permitted-uses-of-accrued-zcg-funds).
A loss caused by a fall in the price of an asset, or by closing a hedge at a
loss, is not a Taking if the action that led to it complied with this section.

## Theft and loss

Theft or accidental loss of Accrued ZCG Funds is not a Taking. The "Security
precautions" section of ZIP 1016 [^zip-1016-security] continues to apply. Any
amount recovered after a theft or loss is Accrued ZCG Funds.

## Legal compulsion

If a Controlling Organization is legally compelled to transfer, freeze, or
surrender Accrued ZCG Funds, it SHALL:

* resist the compulsion by reasonable legal means, where that is lawful and has
  a reasonable prospect of success;
* publicly disclose the amount affected, the legal basis, and the steps it took,
  as soon as the law allows; and
* seek the return of the funds to the ZCG program where possible.

A Controlling Organization MUST NOT seek, invite, or consent to legal process
for the purpose of bringing about a Taking that this ZIP would otherwise
prohibit.

## Future changes to ZCG funding

### Changes to the Accrual Rate

A ZIP adopted after the Protection Date MAY change the Accrual Rate, including
by increasing it, reducing it, ending it, or creating a new ZCG Funding Stream.
Such a change:

* MUST apply only to blocks mined at or after the activation height of the
  network upgrade that deploys it; and
* MUST NOT affect Accrued ZCG Funds, including funds that accrue between the
  adoption of that ZIP and its activation.

### Administrative changes

This ZIP does not prohibit a later ZIP from making administrative changes that
do not reduce or redirect Accrued ZCG Funds and do not change their Permitted
Uses. Examples are:

* changing the recipient address of a ZCG Funding Stream to another address
  controlled by the ZCG program's administrator, as in ZIP 2008 [^zip-2008];
* transferring administration of the ZCG program, with all Accrued ZCG Funds,
  to a successor administrator under [Succession](#succession);
* adding transparency, reporting, conflict-of-interest, or security
  requirements; and
* changing how the ZCG Committee or the Treasury Committee is selected,
  provided that the change does not result in Accrued ZCG Funds being used
  other than for a Permitted Use, and does not remove the separation required
  by [Separation of grant and treasury decisions](#separation-of-grant-and-treasury-decisions).

### Changes to the grant rules

No later ZIP SHALL change the Permitted Uses of Accrued ZCG Funds, or change the
Reference Text as it applies to Accrued ZCG Funds.

A later ZIP that amends the "Zcash Community Grants (ZCG)" section of ZIP 1015
MAY apply its changes to funds that accrue after that ZIP takes effect,
provided that those funds remain restricted to grants for the Zcash ecosystem
and their administration.

### Consensus changes

No network upgrade SHALL freeze, invalidate, make unspendable, reassign, or
otherwise change the spendability of an output holding Accrued ZCG Funds,
except as a side effect of a change that applies equally to all outputs of the
same type, such as the deprecation of a value pool. In that case the ZCG
program MUST be given the same means of migrating its funds as any other
holder.

Developers of Zcash consensus node software SHOULD NOT implement, and node
operators SHOULD NOT run, a consensus change that singles out outputs holding
Accrued ZCG Funds.

<div class="note"></div>

ZIP 1016 notes that nothing forces node developers to implement any particular
proposal [^zip-1016-admin]. The requirements in this section record social
consensus in the same sense.

### ZIP 1015 enforcement remedy

ZIP 1015 provides that a substantial violation of FPF's obligations, not
promptly remedied, will result in node software that removes ZCG's Dev Fund
slice and allocates it to the Deferred Dev Fund Lockbox
[^zip-1015-enforcement]. That remedy changes only the Accrual Rate and remains
available. It MUST NOT be extended to Accrued ZCG Funds.

## Succession

If FPF stops administering the ZCG program for any reason, including its
dissolution, a transition of ZCG to an independent organization under the
section "Furthering Decentralization" of ZIP 1015
[^zip-1015-decentralization], or a legal inability to continue, then all
Accrued ZCG Funds SHALL be transferred to a successor administrator that:

* is selected through the process that selects the ZCG Committee under the
  Reference Text, or, if that process no longer exists, through a process
  specified in a ZIP;
* agrees in writing, before the transfer, to be bound by this ZIP and the
  constraints of the Reference Text; and
* publishes that agreement.

Until a successor is in place, the outgoing administrator SHALL continue to
hold the Accrued ZCG Funds for the ZCG program. If the ZCG program cannot
continue, Accrued ZCG Funds SHALL be applied to the purpose closest to the
Permitted Uses, namely grants for the Zcash ecosystem, and SHALL NOT be
distributed, burned, or used for any other purpose.

## Entrenchment

This ZIP MAY be amended to strengthen the protection of Accrued ZCG Funds, to
correct errors, or to make changes allowed by
[Administrative changes](#administrative-changes). It SHALL NOT be amended,
replaced, or obsoleted in a way that would permit a Taking.

A later ZIP SHALL NOT be interpreted as repealing, limiting, or overriding any
part of this ZIP by implication. A ZIP that is intended to do so MUST say so in
its preamble, using the `Updates` or `Obsoletes` field, and in its abstract.

The ZIP Editors SHOULD treat a draft ZIP that requires or authorizes a Taking
as conflicting with this ZIP, and SHOULD ask its Owners to address this ZIP
explicitly before the draft is assigned a number or advanced in status.

A proposal to amend this ZIP in a way that would permit a Taking SHOULD, at a
minimum, be put to both a coinholder-amount voting round and a ZCAP poll (or
their successors). This is a minimum bar for consideration, and does not
authorize a Taking.

## Legal commitment by FPF

FPF SHALL enter into, and publish, a legal commitment, prepared with Cayman
Islands counsel, that:

1. irrevocably restricts all Accrued ZCG Funds to the Permitted Uses;
2. prohibits each transfer listed in [Prohibited transfers](#prohibited-transfers);
3. states that no later ZIP, vote, or community decision can release that
   restriction;
4. binds any successor administrator, and requires FPF to impose the same
   restriction on any custodian or Autonomous Entity that holds Accrued ZCG
   Funds;
5. gives effect to the separation of grant and treasury decisions required by
   this ZIP; and
6. names at least one party, independent of FPF, the ZCG Committee, and the
   Treasury Committee, with standing to enforce it.

The parties to the commitment SHOULD include the Zcash Foundation and at least
one other organization that does not hold Accrued ZCG Funds.

FPF SHOULD consider, with its counsel, whether a stronger structure is
available, such as an amendment to its constitution or holding Accrued ZCG
Funds through a purpose trust with an independent enforcer.

If FPF determines that it cannot lawfully give this commitment in full, it SHALL
publish that determination with its reasons, and SHOULD publish the strongest
commitment that it can give.

## ZCG Treasury Committee

### Formation

ZCG SHALL establish a ZCG Treasury Committee no later than 45 days after the
Activation Date.

The ZCG Committee SHALL make the initial decisions needed to establish the
Treasury Committee, namely:

* appointing its initial members;
* setting the initial term of each member; and
* adopting its initial charter.

The ZCG Committee SHALL publish these decisions on the Zcash Community Forum
when they are made. After the Treasury Committee is established, the ZCG
Committee has no further role in it except as required by this ZIP.

### Membership

The Treasury Committee MUST have at least three members.

No person SHALL be a member of both the ZCG Committee and the Treasury
Committee at the same time.

No person who is a member of the ZCG Committee on the Activation Date SHALL be
appointed to the Treasury Committee, even if they later leave the ZCG
Committee. Former members who left the ZCG Committee before the Activation
Date are eligible.

The restrictions on association with BP/ECC, ZF, and FPF in point 7 of the
Reference Text apply to the Treasury Committee in the same way as to the ZCG
Committee. A majority of Treasury Committee members MUST NOT have an
association, as defined in that point, with FPF.

Members SHOULD have relevant experience, such as in treasury management,
finance, risk management, or digital asset custody.

### Charter

The initial charter MUST specify:

* the length of members' terms, which SHOULD be staggered;
* how later members are selected, which SHOULD be by ZCAP or a successor
  process, in the same way as members of the ZCG Committee;
* how members may be removed;
* quorum and voting rules;
* a personal trading policy meeting the requirements of
  [Conflicts of interest and personal trading](#conflicts-of-interest-and-personal-trading);
  and
* how the charter may be amended.

The charter MUST NOT give the ZCG Committee any power to remove Treasury
Committee members, to direct Treasury Decisions, or to amend the charter.

Compensation of Treasury Committee members, if any, SHALL be determined in the
same way as compensation of ZCG Committee members under point 9 of the
Reference Text, and is an administration expense.

### Authority

Treasury Decisions made by the Treasury Committee are final and do not require
the approval of the ZCG Committee or FPF's board, but are subject to veto if FPF
determines that they would violate Cayman Islands law or FPF's reporting
requirements or other obligations, in the same way as ZCG Committee decisions
under point 6 of the Reference Text. FPF SHALL execute Treasury Decisions that
are not vetoed, and SHALL publish the reasons for any veto.

The Treasury Committee has no authority to make a Taking.

### Conflicts of interest and personal trading

Each Treasury Committee member MUST disclose, on appointment and in each
quarterly report, whether they hold, or have a financial interest in, ZEC or
financial instruments whose value depends on the price of ZEC, and the
approximate size of that holding in ranges set by the charter.

A Treasury Committee member MUST NOT trade ZEC, or instruments whose value
depends on the price of ZEC, while they know of a Treasury Decision that has not
yet been fully executed and disclosed, or within a period set by the charter
before and after such a decision.

A Treasury Committee member MUST recuse themselves from a Treasury Decision in
which they have a personal financial interest other than their general holding
of ZEC, such as an interest in a proposed counterparty or custodian.

### Transparency of the Treasury Committee

The Treasury Committee SHALL publish minutes of each meeting within 14 days of
the meeting. Details of a planned trade or hedge MAY be withheld from the
minutes until it has been executed, and SHALL be published no later than ZCG's
next quarterly report after execution.

## Separation of grant and treasury decisions

### Treasury Decisions

The following are Treasury Decisions:

* buying, selling, or converting ZEC or any other asset held as Accrued ZCG
  Funds, including the amount and timing of any sale or purchase;
* setting asset allocation and the size of any liquidity reserve;
* opening, adjusting, or closing a hedging position;
* selecting custodians, exchanges, banks, and other treasury counterparties,
  and, together with FPF, setting the custody and signing arrangements for
  Accrued ZCG Funds;
* setting the Program Budget; and
* preparing, adopting, and updating the Treasury Plan.

### Grant Decisions

The following are Grant Decisions:

* approving, rejecting, modifying, renewing, or terminating grants;
* issuing requests for proposals;
* setting and assessing grant milestones; and
* approving disbursements from the Discretionary Budget under point 8 of the
  Reference Text.

### Rules on separation

The ZCG Committee MUST NOT make Treasury Decisions.

The Treasury Committee MUST NOT make Grant Decisions, and MUST NOT make a
Treasury Decision for the purpose of favoring or disfavoring a particular grant
or applicant.

The ZCG Committee MUST NOT approve a grant, or a disbursement from the
Discretionary Budget, that would cause total commitments in a budget period to
exceed the amount set for that period in the Program Budget. The ZCG Committee
MAY ask the Treasury Committee to amend the Program Budget, and SHALL publish any
such request.

Whether a grant is denominated in ZEC or in another currency is a Grant
Decision, but the ZCG Committee SHALL follow any policy on grant denomination
set in the Treasury Plan.

## Interim restriction on the grants committee

From the Activation Date until the Treasury Committee is established, the ZCG
Committee MUST NOT make any decision to buy, sell, or convert ZEC, and MUST NOT
set or change any budget.

During that period, FPF MAY convert ZEC only to the extent needed to pay grant
installments and administration expenses that were approved before or during
that period and that fall due within the following 30 days. Such conversions
SHALL be made at or shortly before the time of payment, without discretion as
to timing, and SHALL be reported in ZCG's next quarterly report.

The ZCG Committee MAY continue to make Grant Decisions during that period.

## Program Budget

The Treasury Committee SHALL set a Program Budget for each calendar year,
stating the maximum total amount that may be committed in that year for:

* grants; and
* administration expenses, including the Discretionary Budget.

The Program Budget MUST provide for the Discretionary Budget and committee
compensation as determined by ZCAP under points 8 and 9 of the Reference Text.

The Treasury Committee SHALL publish the Program Budget, and any amendment to
it, on the Zcash Community Forum within 7 days of adopting it.

Until the first Program Budget is adopted, no budget limit under this ZIP
applies to Grant Decisions.

## Treasury Plan

### Deadline

The Treasury Committee SHALL publish the Treasury Plan on the Zcash Community
Forum and on the ZCG website no later than 31 March 2027. If the Treasury
Committee is established later than 30 January 2027, the deadline is instead
60 days after it is established.

The Treasury Committee SHOULD publish a draft of the Treasury Plan for comment
at least 21 days before publishing the final version, and SHOULD respond
publicly to substantive comments.

FPF SHALL provide the Treasury Committee with the financial information,
custody details, and professional support that it reasonably needs to prepare
the Treasury Plan. The cost of independent financial or legal advice for this
purpose is an administration expense.

### Ten-year budget

The Treasury Plan MUST include a budget for each calendar year from 2027 to
2036 inclusive that:

1. states the balance of Accrued ZCG Funds by asset, with its value in ZEC and
   in US dollars, as of a stated recent date;
2. projects income under at least the following Accrual Rate scenarios:
   * the ZCG Funding Stream continues to its scheduled end at Mainnet height
     6132390 and is not renewed;
   * the ZCG Funding Stream is renewed after that height at its current
     percentage of the block subsidy; and
   * the ZCG Funding Stream ends at the first network upgrade after the
     Treasury Plan is published;
3. considers at least three ZEC price scenarios, one of which assumes that the
   price of ZEC falls by at least 75% from its price at the time the Treasury
   Plan is prepared and does not recover during the budget period;
4. sets out planned spending by category, including at least major grants,
   smaller grants and community programs, requests for proposals, and
   administration (including the Discretionary Budget, committee compensation,
   and treasury costs);
5. shows existing commitments separately from planned new spending;
6. states the expected runway in each scenario; and
7. states the minimum spending needed to keep the ZCG program operating, and
   how long existing Accrued ZCG Funds alone could sustain it.

### Treasury policy

The Treasury Plan MUST include a treasury policy that specifies:

1. target ranges for holdings in ZEC, fiat currency, stablecoins, and any other
   asset, with reasons;
2. a minimum liquidity reserve, held in assets with low price risk, sufficient
   to pay committed grants for a stated period;
3. custody and key management arrangements, including signing thresholds and
   backups, and how they meet the "Security precautions" section of ZIP 1016;
4. whether and how ZEC holdings are kept in shielded pools, and how the
   community can verify balances, for example by published viewing keys or
   periodic attestations;
5. limits on exposure to any single bank, custodian, exchange, stablecoin
   issuer, or other counterparty;
6. confirmation that Accrued ZCG Funds will not be lent to related parties,
   pledged for unrelated obligations, or used for speculative trading, and
   that leverage will be used, if at all, only as part of a hedge described in
   the hedging strategy;
7. a policy on whether grants are denominated in ZEC, in US dollars, or in a
   mix; and
8. how treasury actions will be reported in ZCG's quarterly reports and
   dashboard.

### Hedging strategy

The Treasury Plan MUST include a strategy for managing the risk that a fall in
the price of ZEC leaves ZCG unable to meet its commitments or to sustain its
program. The strategy MUST:

1. measure ZCG's exposure, meaning the difference between its ZEC holdings and
   its obligations fixed in US dollars or other currencies, now and over the
   budget period;
2. describe the methods to be used, which MAY include scheduled conversion of
   part of each period's income, a reserve in low-risk assets matched to
   committed grants, denominating some grants in ZEC, buying put options or
   entering into collars, or other methods;
3. for each method, state its expected cost, its counterparty and custody
   risks, any legal or regulatory constraints, and any expected effect on the
   ZEC market, such as from regular sales;
4. set limits on the size and type of positions, and ensure that no position
   increases ZCG's overall exposure to the price of ZEC;
5. set a schedule or triggers for review and rebalancing; and
6. explain how the strategy balances reducing risk against keeping ZCG's
   interests aligned with the success of ZEC.

### Updates and reporting

The Treasury Committee SHALL review the Treasury Plan at least once a year, and
SHALL publish an updated Treasury Plan, extended so that it covers the next ten
calendar years, no later than 31 March of each year from 2028.

Each ZCG quarterly report required by ZIP 1015 SHALL include:

* the balance of Accrued ZCG Funds by asset, with its value in ZEC and in US
  dollars;
* the treasury actions taken in the quarter and their results; and
* actual commitments and spending compared with the Program Budget, with an
  explanation of any material difference.

### Status of the Treasury Plan obligations

The obligations in [Program Budget](#program-budget) and
[Treasury Plan](#treasury-plan) are added to the obligations that FPF accepts on
behalf of ZCG under the section "Transparency and Accountability" of ZIP 1015
[^zip-1015-transparency].

## Enforcement

Any member of the community MAY publicly report a suspected breach of this ZIP.
The Controlling Organization concerned SHALL respond publicly within 30 days.

A breach of this ZIP by FPF is a violation of FPF's obligations under ZIP 1015,
to which the remedy in [ZIP 1015 enforcement remedy](#zip-1015-enforcement-remedy)
applies, affecting only the Accrual Rate.

The legal commitment described in
[Legal commitment by FPF](#legal-commitment-by-fpf) is enforceable by the
parties named in it, independently of the ZIP process.

A Controlling Organization that permits a prohibited transfer SHOULD restore
the amount to the ZCG program from its own resources.

## Changes to ZIP 1015

In the section "Zcash Community Grants (ZCG)", after the paragraph beginning
"FPF SHALL be contractually required to recognize the ZCG slice of the Dev Fund
as a Restricted Fund donation", insert:

> Funds that have accrued to Zcash Community Grants are protected as specified
> in ZIP [this ZIP]. They MUST NOT be reduced, redirected, burned, or otherwise
> taken by any later ZIP, network upgrade, vote, or agreement, and MUST be used
> only for the purposes described in this section. A later ZIP MAY change only
> the rate at which new funds accrue.
>
> Treasury management decisions for these funds, including any decision to buy
> or sell ZEC and the setting of budgets, are made by the ZCG Treasury
> Committee as specified in ZIP [this ZIP]. The ZCG Committee MUST NOT make
> such decisions.

In the section "Transparency and Accountability", add to the list of
obligations:

> * Publication and annual update of a Program Budget and of a ten-year budget,
>   treasury plan, and ZEC-depreciation hedging strategy, as specified in
>   ZIP [this ZIP].

## Changes to ZIP 1016

In the section "Administrative obligations and constraints", after the first
paragraph, insert:

> Funds received by Zcash Community Grants under this ZIP are Accrued ZCG Funds
> as defined in ZIP [this ZIP], and are protected and managed as specified
> there.

## Testnet-specific considerations

This ZIP has no effect on Testnet. Testnet funds are not Accrued ZCG Funds.

## Open questions

* Should administration expenses remain Permitted Uses of Accrued ZCG Funds, as
  in ZIP 1015, or should Accrued ZCG Funds be restricted to grants alone? This
  draft keeps them, because the program cannot operate without them.
* Should the definition of a grant be fixed for all ZCG funds, including those
  that accrue in future, rather than only for funds already accrued?
* The requirement that the ZCG Committee make "the initial decisions" for the
  Treasury Committee is read here as appointing its first members, setting
  their terms, and adopting its first charter. Should it also cover the first
  Program Budget?
* Should the size of the Discretionary Budget move from ZCAP to the Treasury
  Committee, given that the Treasury Committee sets the Program Budget?
* Is the 30-day exception for conversions needed to pay approved grants during
  the interim period acceptable, or should all conversions wait for the
  Treasury Committee?
* Should consultation through a coinholder-amount voting round and a ZCAP poll
  be a condition of activation rather than a recommendation?
* Whether Cayman Islands law allows FPF to give an irrevocable restriction with
  an independent enforcer, and who that enforcer should be, requires advice
  from FPF's counsel.
* For the 31 March 2027 deadline to be met without the 60-day extension, this
  ZIP needs to become Active by mid-December 2026.


# Rationale

## Rationale for protecting past funds but not future funding

The community has a strong interest in being able to change how much new
issuance goes to grants, including stopping it. Its interest in being able to
take funds already issued for a stated purpose is much weaker, and exercising
that ability has real costs for grantees, for FPF, and for confidence in the
neutrality of Zcash governance. Treating the two separately lets the first
debate continue without the second.

## Rationale for reusing the ZIP 1015 permitted uses

The aim is to preserve the terms on which the funds were issued. Reusing ZIP
1015's restriction keeps the ZCG Committee's existing discretion and avoids a
new set of rules for grantees. Fixing the Reference Text at the Activation Date
prevents a later edit to ZIP 1015 from widening the meaning of a grant so as to
permit a Taking indirectly.

## Rationale for allowing conversion and hedging

Read literally, a rule that accrued funds may not be moved for any purpose other
than grants could prevent ZCG from converting ZEC to pay a grant denominated in
US dollars, or from hedging. The ZIP therefore treats any action that keeps the
value inside the restricted fund as treasury management, and requires the
policy governing it to be published.

## Rationale for a separate Treasury Committee

Separating the people who choose grants from the people who decide when to sell
ZEC reduces the risk that grant pressure drives poorly timed sales, and limits
the number of people with advance knowledge of ZCG's trades. It is a common
arrangement in endowments and foundations, where an investment or finance
committee is distinct from the program committee. Giving the ZCG Committee the
initial appointments lets the new committee start quickly, while the charter
restrictions prevent the grants committee from controlling it afterwards.

The interim restriction prevents the grants committee from making large
discretionary sales or purchases while the new committee is being formed. The
narrow exception for conversions needed to pay approved grants is included so
that grantees are not left unpaid during that period.

## Rationale for the entrenchment approach

A ZIP records community consensus and cannot by itself prevent a later ZIP,
with later consensus, from reversing it. This ZIP does not rely on its own text
alone. It combines three measures:

* a procedural rule in the ZIP process, under which a later ZIP cannot repeal
  this one by implication and the ZIP Editors are asked to treat conflicting
  drafts as such;
* a published legal commitment by FPF, which a later ZIP cannot undo, and which
  gives an independent party standing to enforce the restriction; and
* a request that node developers and operators not implement or run a
  consensus change aimed at ZCG's outputs, which is the only way funds already
  paid to FPF-controlled addresses could be taken on-chain.

Entrenchment should be rare in the ZIP process. It is used here because it
protects a past act of issuance rather than a future policy choice, it restates
a restriction FPF has already accepted, and without it any ZCG balance remains
exposed to a single future vote.

## Rationale for consulting both coinholders and ZCAP

Neither ZIP 1015 nor ZIP 1016 gives coinholder votes a formal role over ZCG
funds; coinholder votes under ZIP 1016 are binding only for the
Coinholder-Controlled Fund, and the ZCG Committee is selected by ZCAP. Asking
both groups gives broader evidence of support, and avoids implying that a
coinholder-amount voting round alone could later authorize a Taking.

## Rationale for the deadline

A deadline of 31 March 2027 allows time to form the Treasury Committee and hold
a comment period on a draft plan, and puts the first Treasury Plan in place well
before the scheduled end of the ZCG Funding Stream in late 2028.


# References

[^BCP14]: [Information on BCP 14, "RFC 2119: Key words for use in RFCs to Indicate Requirement Levels" and "RFC 8174: Ambiguity of Uppercase vs Lowercase in RFC 2119 Key Words"](https://www.rfc-editor.org/info/bcp14)

[^protocol-networks]: [Zcash Protocol Specification, Version 2026.8.0. Section 3.12: Mainnet and Testnet](protocol/protocol.pdf#networks)

[^zip-0000]: [ZIP 0: ZIP Process](zip-0000.rst)

[^zip-0214]: [ZIP 214: Consensus rules for a Zcash Development Fund](zip-0214.rst)

[^zip-1015]: [ZIP 1015: Block Subsidy Allocation for Non-Direct Development Funding](zip-1015.rst)

[^zip-1015-zcg]: [ZIP 1015: Block Subsidy Allocation for Non-Direct Development Funding, Zcash Community Grants (ZCG)](zip-1015.rst#zcash-community-grants-zcg)

[^zip-1015-decentralization]: [ZIP 1015: Block Subsidy Allocation for Non-Direct Development Funding, Furthering Decentralization](zip-1015.rst#furthering-decentralization)

[^zip-1015-transparency]: [ZIP 1015: Block Subsidy Allocation for Non-Direct Development Funding, Transparency and Accountability](zip-1015.rst#transparency-and-accountability)

[^zip-1015-enforcement]: [ZIP 1015: Block Subsidy Allocation for Non-Direct Development Funding, Enforcement](zip-1015.rst#enforcement)

[^zip-1015-funding-streams]: [ZIP 1015: Block Subsidy Allocation for Non-Direct Development Funding, Funding Streams](zip-1015.rst#funding-streams)

[^zip-1016]: [ZIP 1016: Community and Coinholder Funding Model](zip-1016.md)

[^zip-1016-zcg]: [ZIP 1016: Community and Coinholder Funding Model, Zcash Community Grants](zip-1016.md#zcash-community-grants)

[^zip-1016-disbursement]: [ZIP 1016: Community and Coinholder Funding Model, Disbursement process](zip-1016.md#disbursement-process)

[^zip-1016-admin]: [ZIP 1016: Community and Coinholder Funding Model, Administrative obligations and constraints](zip-1016.md#administrative-obligations-and-constraints)

[^zip-1016-security]: [ZIP 1016: Community and Coinholder Funding Model, Security precautions](zip-1016.md#security-precautions)

[^zip-2008]: [ZIP 2008: Update to `FS_FPF_ZCG_H3` address list](zip-2008.md)

[^zips-pr-1414]: [zcash/zips pull request 1414](https://github.com/zcash/zips/pull/1414)

[^zips-pr-1423]: [zcash/zips pull request 1423](https://github.com/zcash/zips/pull/1423)

[^zips-pr-1428]: [zcash/zips pull request 1428](https://github.com/zcash/zips/pull/1428)

[^forum-zcg-taper]: [Zcash Community Forum, topic 58566 (ZCG proposal, 29 October 2026)](https://forum.zcashcommunity.com/t/58566)

[^forum-fpf-reply]: [Zcash Community Forum, topic 58611, post 24 (FPF reply, 30 October 2026)](https://forum.zcashcommunity.com/t/58611/24)
