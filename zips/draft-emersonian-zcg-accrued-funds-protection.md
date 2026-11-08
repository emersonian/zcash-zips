    ZIP: Unassigned
    Title: Protection of Accrued Zcash Community Grants Funds
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
Privacy Foundation" (or "FPF"), "Autonomous Entities", "Discretionary Budget",
and "Restricted Fund" in this document are to be interpreted as defined or
used in ZIP 1015 [^zip-1015].

The terms "Coinholder-Controlled Fund" and "Key-Holder Organizations" in this
document are to be interpreted as described in ZIP 1016 [^zip-1016].

The term "Zcash Community Advisory Panel" (or "ZCAP") is to be interpreted as
defined in ZIP 1015 [^zip-1015].

"ZEC" refers to the native currency of Zcash on Mainnet.

A **coinholder-amount voting round** is a coinholder vote held under ZIP 1016
[^zip-1016-disbursement], in which each ballot is weighted by the amount of ZEC
that the voter proves control of, conducted under the rules for such votes that
are in effect at the time the vote is held.

A **ZCG Funding Stream** is any funding stream whose recipient is FPF (or a
successor administrator) for the use of Zcash Community Grants. As of writing
this means `FS_FPF_ZCG` [^zip-1015-funding-streams] and `FS_FPF_ZCG_H3`
[^zip-0214] [^zip-1016-zcg], and it includes any later funding stream defined
for the same purpose under any name.

**Accrued ZCG Funds** means:

1. every amount paid to a recipient address of a ZCG Funding Stream, from the
   block in which the payment is mined onward;
2. every amount donated, granted or otherwise contributed to FPF (or a
   successor administrator) for the use of Zcash Community Grants, from the
   time it is received;
3. any amount that has been returned to the program, such as an unspent
   grant tranche, a clawed-back grant payment, or an unspent part of the
   Discretionary Budget; and
4. everything that any of the above is converted into or earns. This includes
   fiat currency, stablecoins, other digital assets, bank deposits, money
   market instruments, interest, yield, and the proceeds of any hedging
   position entered into under the Treasury Plan.

Accrued ZCG Funds stay Accrued ZCG Funds for as long as they are held,
whatever account, wallet, custodian or asset they are held in. Funds stop being
Accrued ZCG Funds only when they are paid out for a Permitted Use.

A **Permitted Use** is a use of funds described in
[Permitted uses of Accrued ZCG Funds](#permitted-uses-of-accrued-zcg-funds).

The **Reference Text** of ZIP 1015 is the text of the section "Zcash Community
Grants (ZCG)" of ZIP 1015 [^zip-1015-zcg], together with the text of any ZIP
that amends that section and that is Active or Final on the Effective Date, as
those texts read on the Effective Date. Non-normative note: the Reference Text
is fixed so that a later edit to ZIP 1015 cannot widen the meaning of "grant"
and so open a back door around this ZIP. The ZIP Editors SHOULD record the
git commit of the zcash/zips repository that holds the Reference Text when
this ZIP becomes Active.

A **Controlling Organization** is any organization or person that holds,
administers, has signing authority over, acts as custodian of, or can direct
the movement of any Accrued ZCG Funds. This includes, but is not limited to:

* FPF, its board of directors, its supervisor, and its members;
* the ZCG Committee and each of its members, when acting in that role;
* any successor administrator of the ZCG program, including any independent
  organization formed under the section "Furthering Decentralization" of
  ZIP 1015 [^zip-1015-decentralization];
* the Zcash Foundation, Electric Coin Company, Bootstrap Project, any
  Key-Holder Organization, and any other organization, if it ever holds or
  controls Accrued ZCG Funds; and
* any custodian, trustee, signer, or service provider that holds Accrued ZCG
  Funds on behalf of any of the above.

A **Taking** is any action that causes Accrued ZCG Funds to leave the control of
the ZCG program other than for a Permitted Use, or that makes them unusable for
a Permitted Use. See [Prohibited transfers](#prohibited-transfers) for a
non-exhaustive list.

The **Accrual Rate** is the share of the block subsidy (or any other
protocol-level issuance) paid to ZCG Funding Streams, together with the start
and end heights of those streams.

The **Effective Date** is the date on which this ZIP takes effect, as described
in [Adoption](#adoption).

The **Treasury Plan** is the plan that ZCG must publish under
[Ten-year budget, treasury plan and hedging strategy](#ten-year-budget-treasury-plan-and-hedging-strategy).


# Abstract

This ZIP makes three commitments about the funds that Zcash Community Grants
has already received, and will receive, under the ZCG funding stream.

First, it bars anyone, by any ZIP, network upgrade, vote, agreement or other
means, from taking away funds that have already accrued to ZCG. Balances that
ZCG already holds are left exactly where they are.

Second, it bars FPF, the ZCG Committee and every other organization that holds
or controls those funds from allowing them to be moved for any purpose other
than grants as defined in the ZCG section of ZIP 1015 (including the
administration expenses that section already allows). In particular, accrued
ZCG funds cannot be sent to the Network Sustainability Mechanism, burned, sent
to a lockbox, sent to the Coinholder-Controlled Fund, or used for FPF's own
operations.

Third, it says that the only thing a future ZIP may change about ZCG funding is
the rate at which new funds accrue. A future ZIP can reduce the ZCG funding
stream, including to zero, but only for blocks mined after that ZIP takes
effect.

It also orders ZCG to publish, by 31 March 2027, a ten-year budget, a treasury
plan, and a strategy for hedging the risk that the value of ZEC falls.

Finally, it addresses the obvious question of how one ZIP can bind later ZIPs,
by combining an entrenchment clause, a legal commitment by FPF that does not
depend on the ZIP process, and a request that node developers not implement any
consensus change that seizes funds already paid out.


# Motivation

## Recent proposals to take ZCG's existing funds

In October 2026 several proposals were made to end or redirect ZCG funding. As
of late October 2026 these included:

* a draft ZIP that would end the ZCG funding stream and redirect it to the
  Network Sustainability Mechanism (NSM) (zcash/zips#1414, since closed);
* a draft ZIP that would redirect the stream to a new lockbox and also
  require the ZCG Committee to send 50,000 ZEC of its existing balance to a
  provably unspendable address, to be credited to the NSM at a later network
  upgrade (zcash/zips#1428);
* a draft ZIP that would wind ZCG down, subject to Cayman Islands legal advice
  and changes to the relevant agreements (zcash/zips#1423); and
* a ZCG forum post proposing a voluntary taper, including sending about
  36,200 ZEC to the NSM.

Reasonable people disagree about how much block subsidy should go to ZCG in
the future. That is a legitimate question for the community, and this ZIP does
not answer it. But two of these proposals reach back and take funds that were
issued, under rules the community had already agreed, for a specific
purpose. That is a different kind of act, and it should not be on the table.

## Why accrued funds should be protected

1. **The funds were issued for a stated purpose.** ZIP 1015 says that the ZCG
   funds "MUST be used exclusively for issuing Zcash Community Grants to
   external parties that are independent of the FPF or to Autonomous Entities
   operating under the FPF umbrella", and that FPF must hold them as a
   Restricted Fund. Every block that paid the ZCG stream was mined, and every
   ZEC in it was issued, on that understanding. Changing the purpose of money
   after it has been issued breaks the bargain that justified issuing it.

2. **Grantees and applicants rely on it.** Teams plan hiring, multi-year work
   and milestones around ZCG's ability to pay. If the balance can be taken by
   a later vote, every multi-year grant carries political risk, and the best
   teams will discount ZCG grants accordingly or not apply.

3. **Legal exposure.** ZIP 1015 requires FPF to recognize the ZCG slice "as a
   Restricted Fund donation under the above constraints". Under Cayman
   Islands law a foundation company that sends restricted funds to a purpose
   outside the restriction, or to an address from which nobody can ever
   recover them, may expose its directors to claims. FPF itself said in
   October 2026 that its counsel had considered such a donation only on the
   condition of "an affirmative community vote in favor of the proposal and
   an accepted ZIP", neither of which is defined in any ZIP. This ZIP removes
   the ambiguity: no such vote or ZIP can authorize it.

4. **Credible neutrality and precedent.** Zcash's value rests partly on the
   promise that funds that have been validly issued are not seized by
   later political action. Taking funds from a disfavored recipient is the
   same kind of act, in governance terms, as freezing a disfavored user's
   coins. A rule that the community does not do the first makes it easier to
   say that it will never do the second.

5. **Separating two decisions.** The community needs to keep its full ability
   to decide how much to fund grants in the future. Protecting the past while
   leaving the future rate open lets that debate happen without also being a
   fight over money that was already committed.

## Why a ten-year plan and hedging strategy

ZCG's funding stream is scheduled to end at Zcash's third halving (Mainnet
height 6132390 under ZIP 214 Revision 3 [^zip-0214], expected around late
2028), and it may end sooner if a future ZIP reduces the Accrual Rate. ZCG's
balance is held largely in ZEC, while most grant obligations are understood by
grantees in US dollar terms. A fall in the price of ZEC can therefore cut ZCG's
real ability to fund work by a large fraction within months, even if no ZIP
changes anything.

If accrued funds are protected forever, ZCG has a matching responsibility to
manage them well over a long horizon: to show the community how long they will
last, what they will be spent on, and how ZCG will avoid being forced to stop
funding work in the middle of a downturn. As of writing, ZCG publishes
quarterly reports and a dashboard under ZIP 1015, but no public multi-year
budget, treasury policy, or hedging policy.


# Requirements

* Funds that have accrued to ZCG cannot be reduced, redirected, burned or
  otherwise taken by any later ZIP, network upgrade, vote, or agreement.
* Accrued ZCG funds can only be used for grants and grant administration as
  defined in ZIP 1015, and every organization that holds or controls them is
  bound by this.
* A future ZIP can still change the rate at which new funds accrue to ZCG,
  including reducing it to zero, for future blocks.
* The protection does not depend only on the ZIP process, which cannot bind
  itself, but is also backed by a legal commitment that a later ZIP cannot
  undo.
* ZCG publishes a ten-year budget, treasury plan and ZEC-depreciation hedging
  strategy by 31 March 2027, and keeps them current.
* Prudent treasury management, including converting ZEC to other assets to
  reduce risk, is allowed and is not treated as a prohibited transfer, as long
  as the result stays in the restricted fund.


# Non-requirements

* This ZIP does not set or change the Accrual Rate. In particular it does not
  extend, reduce or end the `FS_FPF_ZCG_H3` funding stream.
* This ZIP does not change the ZCG Committee's discretion over which grants
  to fund, how the ZCG Committee is selected, or FPF's legal veto under
  point 6 of the Reference Text.
* This ZIP does not cover the Coinholder-Controlled Fund, the in-protocol
  lockbox, or funds held by any other organization, except where they hold
  Accrued ZCG Funds.
* This ZIP does not prevent FPF from complying with a binding court order,
  sanctions law or other legal requirement that it cannot lawfully refuse. It
  does require such cases to be disclosed (see
  [Legal compulsion](#legal-compulsion)).
* This ZIP does not decide whether the NSM, a new lockbox, or any other use of
  future issuance is a good idea.


# Specification

## Adoption

This ZIP takes effect on the later of:

1. the date on which it becomes Active under ZIP 0 [^zip-0000]; and
2. the date on which FPF publishes the signed legal commitment described in
   [Legal commitment by FPF](#legal-commitment-by-fpf).

That date is the Effective Date.

Because this ZIP limits what later ZIPs may do, it SHOULD have wider support
than an ordinary Process ZIP before it becomes Active. Before the ZIP Editors
change its status to Active, the community SHOULD be asked about it through
both:

* a coinholder-amount voting round, held by the Key-Holder Organizations under
  the rules for such votes in effect at the time; and
* a poll of the Zcash Community Advisory Panel (or its successor), which is the
  body that selects the ZCG Committee under ZIP 1015.

The ZIP Editors SHOULD treat clear approval in both as strong evidence of rough
consensus, and SHOULD publish both results alongside the status change.

Funds that accrued to ZCG before the Effective Date are Accrued ZCG Funds. This
ZIP protects them in the same way as funds that accrue after it.

## Protection of Accrued ZCG Funds

No ZIP, network upgrade, vote (including any coinholder-amount voting round or
ZCAP poll), agreement, resolution, or other governance action, whether made
before or after the Effective Date, SHALL reduce, redirect, recapture, freeze,
burn, or otherwise take any Accrued ZCG Funds.

Any provision of any ZIP that would require or authorize a Taking is, to that
extent, without effect, and no Controlling Organization SHALL act on it. This
applies whatever the provision calls the Taking, for example a "donation",
"contribution", "return", "wind-down", "taper", "rebalancing" or "transfer".

The balances that ZCG holds on the Effective Date, and all later Accrued ZCG
Funds, SHALL be left under the administration of the ZCG program, to be spent
only for Permitted Uses at the discretion of the ZCG Committee.

## Permitted uses of Accrued ZCG Funds

Accrued ZCG Funds MUST be used only for:

1. issuing Zcash Community Grants to external parties that are independent of
   FPF, or to Autonomous Entities operating under the FPF umbrella, as
   described in point 1 of the Reference Text, and subject to points 2 to 7 of
   the Reference Text; and
2. expenses reasonably related to the administration of Zcash Community
   Grants, including the Discretionary Budget and ZCG Committee compensation,
   as described in points 1, 8, 9 and 10 of the Reference Text.

No other use is a Permitted Use. In particular, Accrued ZCG Funds MUST NOT be
used for FPF's internal operations or for any direct expense unrelated to the
administration of Zcash Community Grants, as already required by ZIP 1015.

Non-normative note: this restates ZIP 1015's own restriction rather than
inventing a new one. What is new is that the restriction is made permanent
for funds that have already accrued, binds every organization that holds the
funds rather than only FPF, and cannot be widened by a later ZIP.

### Prohibited transfers

Without limiting the general rule above, no Controlling Organization SHALL
make, sign, approve, or allow any of the following with Accrued ZCG Funds:

* a transfer to the Network Sustainability Mechanism, or to any address,
  output or mechanism intended to be credited to it now or in future;
* a transfer to a provably unspendable address, an `OP_RETURN` output, or any
  other output from which the funds cannot be recovered, or any other burn;
* a transfer to any in-protocol lockbox, to the Coinholder-Controlled Fund, or
  to any fund that is not administered for Permitted Uses;
* a transfer to miners, to coinholders, or to any other class of persons as a
  distribution or refund;
* a transfer to FPF's general funds, to the Zcash Foundation, Electric Coin
  Company, Bootstrap Project, or any other organization, other than as
  payment for a Permitted Use;
* use of the funds as collateral, or as a guarantee, for any obligation that
  is not itself for a Permitted Use; and
* any loan of the funds to a Controlling Organization or to a related party of
  a Controlling Organization.

This list applies whether the transfer is described as voluntary or
mandatory, and whether or not it is approved by the ZCG Committee, the FPF
board, a coinholder-amount voting round, a ZCAP poll, or a ZIP.

### Treasury management is not a Taking

Converting Accrued ZCG Funds from one asset into another, moving them between
accounts, wallets or custodians, and entering into hedging positions, is not a
Taking and is not a prohibited transfer, provided that:

* the resulting assets remain Accrued ZCG Funds, held for the ZCG program and
  accounted for in its Restricted Fund;
* the action is consistent with the Treasury Plan that is in effect at the
  time (or, before the first Treasury Plan is published, with prudent
  practice); and
* the action is reported in ZCG's next quarterly report.

Reasonable transaction costs, custody fees and hedging costs are
administration expenses under point 2 of
[Permitted uses](#permitted-uses-of-accrued-zcg-funds).

Losses from a fall in the price of an asset, or from a hedge that is closed at
a loss, are not a Taking, as long as the action was consistent with the
Treasury Plan.

### Theft, loss and legal compulsion

#### Theft and loss

Theft or accidental loss of Accrued ZCG Funds is not a Taking for the purposes
of this ZIP, but the requirements of the "Security precautions" section of
ZIP 1016 [^zip-1016-security] continue to apply. Any amount recovered after a
theft or loss is Accrued ZCG Funds.

#### Legal compulsion

If a Controlling Organization is legally compelled to transfer, freeze or
surrender any Accrued ZCG Funds (for example by a court order or sanctions
law), it SHALL:

* resist the compulsion by all reasonable legal means, where doing so is
  lawful and has a reasonable prospect of success;
* publicly disclose, as promptly as the law allows, the amount affected, the
  legal basis, and the steps it took; and
* seek the return of the funds to the ZCG program where possible.

A Controlling Organization MUST NOT seek, invite, or consent to a court order,
regulatory action or other legal process for the purpose of achieving a Taking
that this ZIP otherwise forbids.

## Future changes to ZCG funding

### Only the Accrual Rate may change

A ZIP that is adopted after the Effective Date MAY change the Accrual Rate. It
MAY increase it, reduce it, end it, or create a new ZCG Funding Stream. Any
such change:

* MUST apply only to blocks mined at or after the activation height of the
  network upgrade, or the effective date of the process change, that deploys
  it; and
* MUST NOT have any effect on Accrued ZCG Funds, including funds that accrued
  between the adoption of the ZIP and its activation.

Changes that are administrative and do not reduce, redirect, or change the
Permitted Uses of Accrued ZCG Funds are not prohibited by this ZIP. These
include, for example:

* changing the recipient address of a ZCG Funding Stream to another address
  controlled by the ZCG program's administrator, as in ZIP 2008 [^zip-2008];
* transferring administration of the ZCG program, together with all Accrued
  ZCG Funds, to a successor administrator that is bound by this ZIP (see
  [Succession](#succession));
* adding transparency, reporting, conflict-of-interest, or security
  requirements; and
* changing how the ZCG Committee is selected, provided that the change does
  not in practice route Accrued ZCG Funds to anything other than a Permitted
  Use.

No later ZIP SHALL change the Permitted Uses of Accrued ZCG Funds, or change
the Reference Text as it applies to Accrued ZCG Funds. A later ZIP that amends
the "Zcash Community Grants (ZCG)" section of ZIP 1015 MAY apply its changes to
funds that accrue after it takes effect, but only if those changes keep the
use of the funds within grants and grant administration for the Zcash
ecosystem.

Open question for the ZIP Owner: this draft lets a future ZIP narrow or adjust
the grant rules for funds that accrue later, while freezing the rules for funds
already accrued. An alternative is to freeze the definition of "grant" for all
ZCG funds, past and future. The trade-off is that a total freeze makes it
harder to improve the program; the current text tries to keep improvements
possible without opening a path to reuse.

### No consensus change may affect Accrued ZCG Funds

No network upgrade SHALL freeze, invalidate, make unspendable, reassign, or
otherwise change the spendability of any output that holds Accrued ZCG Funds,
except as a side effect of a change that applies in the same way to all
outputs of the same type (for example the deprecation of a value pool, in
which case the ZCG program MUST be given the same migration path as any other
holder).

Developers of Zcash consensus node software SHOULD NOT implement, and node
operators SHOULD NOT run, any consensus change that singles out outputs
holding Accrued ZCG Funds.

Non-normative note: this matches the note in ZIP 1016 that "nothing forces
developers of Zcash consensus node software to implement any particular
proposal". This section is a statement of social consensus to the same
effect, in the other direction.

### Interaction with the ZIP 1015 enforcement remedy

ZIP 1015's "Enforcement" section provides that a substantial violation of FPF's
obligations, not promptly remedied, "will result in a modified version of Zcash
node software that removes ZCG's Dev Fund slice and allocates it to the
Deferred Dev Fund lockbox" [^zip-1015-enforcement]. That remedy changes only the
Accrual Rate for future blocks, and remains available. It MUST NOT be extended
to Accrued ZCG Funds.

If a Controlling Organization breaches this ZIP, the remedies are those in
[Enforcement](#enforcement), and not a Taking.

## Succession

If FPF stops administering the ZCG program for any reason, including its
dissolution, a decision to transition ZCG to an independent organization
under ZIP 1015, or an inability to continue for legal reasons, then all
Accrued ZCG Funds SHALL be transferred to a successor administrator that:

* is selected through the process that selects the ZCG Committee under the
  Reference Text (ZCAP or its successor), or, if that process no longer
  exists, through a process set out in a ZIP;
* agrees in writing, before the transfer, to be bound by this ZIP and by the
  constraints of the Reference Text, including the Restricted Fund
  requirement; and
* publishes that agreement.

Until a successor is in place, the outgoing administrator SHALL keep holding
the Accrued ZCG Funds for the ZCG program, and SHALL NOT transfer them to any
other purpose. If the program truly cannot continue, Accrued ZCG Funds SHALL
be applied to the purpose closest to the Permitted Uses (grants for the Zcash
ecosystem), and SHALL NOT be distributed, burned or used for any other
purpose.

Non-normative note: the last rule is meant to work like the "cy-près"
doctrine used for charitable funds in many legal systems: if the original
purpose fails, the money goes to the nearest purpose, not back into general
circulation.

## Entrenchment

### The problem

A ZIP is a statement of community consensus, recorded by the ZIP Editors. It
has no special power to stop a later ZIP, with later consensus, from saying
the opposite. A rule that says "no later ZIP may change this rule" can, in
principle, be repealed by a later ZIP that says "this rule is repealed". This
ZIP does not pretend otherwise.

Instead, it uses three layers of protection that each make a Taking harder,
and that together make it impractical.

### Layer 1: Procedural entrenchment in the ZIP process

1. This ZIP MAY be amended to strengthen the protection of Accrued ZCG Funds,
   to correct errors, or to make administrative changes allowed by
   [Future changes to ZCG funding](#future-changes-to-zcg-funding). It
   SHALL NOT be amended, replaced or obsoleted in any way that would permit a
   Taking.

2. A later ZIP SHALL NOT be read as repealing, limiting or overriding any part
   of this ZIP by implication. A ZIP that intends to do so MUST say so
   explicitly in its preamble (using "Obsoletes" or "Updates") and in its
   abstract.

3. The ZIP Editors SHOULD treat a draft ZIP that requires or authorizes a
   Taking as conflicting with an Active ZIP, and SHOULD require it to address
   this ZIP explicitly before it is assigned a number or advanced in status.

4. Any proposal to amend this ZIP in a way that would permit a Taking SHOULD,
   at the least, require the same broader support as was sought for this ZIP
   under [Adoption](#adoption): clear approval in both a coinholder-amount
   voting round and a ZCAP poll (or their successors). This is a floor, not a
   way to authorize a Taking; points 1 and 2 still apply.

### Layer 2: A legal commitment that does not depend on the ZIP process

The strongest protection is legal, because a contract or trust restriction
that FPF has entered into cannot be undone by a later ZIP. See
[Legal commitment by FPF](#legal-commitment-by-fpf).

### Layer 3: Social and consensus-layer commitment

[No consensus change may affect Accrued ZCG Funds](#no-consensus-change-may-affect-accrued-zcg-funds)
asks node developers and node operators not to implement or run any change
that singles out ZCG outputs. Because funds already paid to ZCG are held at
ordinary addresses controlled by FPF, the only on-chain way to take them would
be a targeted consensus change of exactly that kind.

### Rationale for entrenchment (non-normative)

Entrenchment is unusual in the ZIP process and should be rare. It is justified
here because:

* the clause protects a past act of issuance, not a future policy choice, so
  it does not stop the community from setting future funding however it
  likes;
* it mirrors a restriction that ZIP 1015 already placed on the funds, and that
  FPF already accepted as a Restricted Fund donation; and
* without it, any balance ZCG holds is always one vote away from being
  taken, which harms grantees and creates legal risk for FPF regardless of
  whether any Taking actually happens.

## Legal commitment by FPF

Before the Effective Date, FPF SHALL enter into, and publish, a legal
commitment, prepared with Cayman Islands counsel, that:

1. irrevocably restricts all Accrued ZCG Funds to the Permitted Uses;
2. forbids each Prohibited Transfer;
3. states that no later ZIP, vote or community decision can release the
   restriction;
4. binds any successor administrator, and requires FPF to impose the same
   commitment on any custodian or Autonomous Entity that holds Accrued ZCG
   Funds; and
5. names at least one party, independent of FPF and of the ZCG Committee, with
   standing to enforce the restriction.

The counterparty or counterparties to the commitment SHOULD include the Zcash
Foundation (which ZIP 1015 already makes responsible for ZCAP) and at least one
other organization that does not hold Accrued ZCG Funds.

FPF SHOULD consider, with its counsel, whether a stronger structure is
available under Cayman Islands law, such as amending its constitution, or
holding Accrued ZCG Funds through a purpose trust with an independent enforcer.

Non-normative note: ZIP 1015 requires FPF to "contractually commit" to its
obligations, but does not name the other party to that contract, and the
restricted-fund agreement and FPF's constitution are not public as of writing.
This ZIP asks for the commitment to be published so that the community can
see who can enforce it.

If FPF declares, with a thorough rationale, that it cannot lawfully give this
commitment in full, it SHALL publish that declaration and SHOULD propose the
strongest commitment it can give. The ZIP Owner MAY then revise this ZIP to
match.

## Ten-year budget, treasury plan and hedging strategy

### Order

The ZCG Committee, with the support of FPF, SHALL prepare and publish a Treasury
Plan on the Zcash Community Forum and on the ZCG website **no later than
31 March 2027**.

The ZCG Committee SHOULD publish a draft of the Treasury Plan for community
comment at least 30 days before publishing the final version, and SHOULD
respond in public to substantive comments.

FPF SHALL give the ZCG Committee all financial information, custody details,
and professional support (including the cost of independent financial advice,
which is an administration expense) that the ZCG Committee reasonably needs to
prepare the Treasury Plan.

This obligation applies whether or not this ZIP's Effective Date has occurred
by then. If the Effective Date has not occurred, ZCG and FPF SHOULD still
publish the Treasury Plan by that date.

### Contents

The Treasury Plan MUST contain the three parts below. Each part SHOULD state its
assumptions and their sources.

#### Part 1: Ten-year budget

A budget for each calendar year from 2027 to 2036 inclusive, that:

1. states the opening balance of Accrued ZCG Funds by asset, and its value in
   ZEC and in US dollars, as of a recent date;
2. projects income under at least these Accrual Rate scenarios:
   * the current stream continues to its scheduled end at Mainnet height
     6132390 (around late 2028) and is not renewed;
   * the stream is renewed after the third halving at the same percentage;
   * the stream is ended at the next network upgrade after the Treasury Plan
     is published; and
3. projects income under at least three ZEC price scenarios, including one in
   which the price of ZEC falls by at least 75% from its level at the time of
   writing and stays there;
4. sets out planned spending by category, including at least: major grants,
   smaller grants and community programs, dedicated resources or requests for
   proposals, and administration (including the Discretionary Budget and
   committee compensation);
5. shows existing commitments (approved grants not yet paid) separately from
   planned new spending;
6. states the runway (the number of years that the program can continue at
   its planned spending) in each scenario; and
7. states the minimum level of spending ZCG would maintain to keep its core
   program running, and how long that could last on existing Accrued ZCG
   Funds alone.

#### Part 2: Treasury plan

A treasury management policy that covers at least:

1. **Asset allocation**: target ranges for holdings in ZEC, fiat currency,
   stablecoins (if any) and any other asset, and the reasons for them;
2. **Liquidity reserve**: a minimum amount, held in assets with low price
   risk, sufficient to pay committed grants for a stated period (for example
   12 months of committed payments);
3. **Custody and security**: who holds the keys or accounts, the signing
   policy (for example multisignature thresholds), how keys are backed up,
   and how this meets the "Security precautions" section of ZIP 1016;
4. **Shielding**: whether and how ZEC holdings are kept in shielded pools,
   and how this is reconciled with transparency to the community (for example
   by publishing viewing keys);
5. **Counterparties**: limits on exposure to any single bank, custodian,
   exchange, stablecoin issuer or other counterparty;
6. **Prohibited activities**: confirming that Accrued ZCG Funds will not be
   lent to related parties, used as collateral for unrelated obligations,
   or used for speculative trading, and that leverage will not be used except
   as part of a hedge described in Part 3;
7. **Grant denomination**: whether grants are denominated in ZEC, in US
   dollars, or in a mix, and how this matches the asset allocation;
8. **Decision-making**: who may approve conversions, transfers and hedges,
   and what requires a ZCG Committee vote; and
9. **Reporting**: how treasury actions will be reported in ZCG's quarterly
   reports and dashboard.

#### Part 3: Strategy for hedging the risk of ZEC depreciation

A strategy for managing the risk that a fall in the price of ZEC makes ZCG
unable to meet its commitments or to keep its program running. It MUST at
least:

1. measure ZCG's exposure: the gap between its ZEC holdings and its
   obligations that are fixed in US dollars or other currencies, now and over
   the budget period;
2. describe the methods ZCG will use, which MAY include, for example:
   scheduled conversion of part of each period's income (dollar-cost
   averaging), holding a reserve in low-risk assets matched to committed
   grants, denominating some grants in ZEC, buying protective options or
   entering into collars, or other instruments;
3. for each method, state its cost, its counterparty and custody risks, any
   legal or regulatory constraints (including under Cayman Islands law and
   FPF's obligations), and any effect on the ZEC market, such as the effect of
   regular sales;
4. set limits on the size and type of positions, and confirm that no hedge
   will be speculative (that is, no position will increase ZCG's overall
   exposure to price movements);
5. set out triggers or a schedule for reviewing and rebalancing; and
6. explain how the strategy balances reducing risk against the value of ZCG
   remaining aligned with the success of ZEC.

Non-normative note: hedging means selling some ZEC or buying protection
against a fall in its price. Some in the community may see that as a vote of
no confidence in ZEC. The Treasury Plan is asked to address that tension
openly rather than avoid it; the main purpose is to protect grantees and the
program from being forced to stop work at the worst time.

### Updates and reporting

The ZCG Committee SHALL review the Treasury Plan at least once a year, and SHALL
publish an updated Treasury Plan, rolled forward so that it always covers the
next ten calendar years, no later than 31 March of each year starting in 2028.

Each ZCG quarterly report required by ZIP 1015 SHALL include:

* the balance of Accrued ZCG Funds by asset, and its value in ZEC and US
  dollars;
* treasury actions taken in the quarter (conversions, transfers between
  custodians, hedges opened or closed) and their results; and
* actual spending against the Treasury Plan budget, with an explanation of any
  material difference.

The Treasury Plan is a planning document. It does not limit the ZCG Committee's
discretion over individual grants, but the ZCG Committee SHOULD explain in its
quarterly reports any decision that departs materially from it.

### Status of this obligation

The obligation to publish and maintain the Treasury Plan is added to the
transparency and accountability obligations that FPF accepts on behalf of ZCG
under the "Transparency and Accountability" section of ZIP 1015
[^zip-1015-transparency]. A failure to publish the Treasury Plan, not promptly
remedied, is therefore subject to ZIP 1015's existing enforcement remedy, which
affects only the Accrual Rate and never Accrued ZCG Funds.

## Enforcement

* Any member of the community MAY publicly report a suspected breach of this
  ZIP. The Controlling Organization concerned SHALL respond publicly within
  30 days.
* A breach of this ZIP by FPF is a substantial violation of FPF's obligations
  under ZIP 1015, to which ZIP 1015's enforcement remedy applies (for future
  accrual only).
* The legal commitment described in
  [Legal commitment by FPF](#legal-commitment-by-fpf) is enforceable by the
  parties named in it, independently of the ZIP process.
* If a Controlling Organization allows a Prohibited Transfer, it SHOULD make
  the ZCG program whole from its own resources.

## Changes to ZIP 1015

In the section "Zcash Community Grants (ZCG)", after the paragraph beginning
"FPF SHALL be contractually required to recognize the ZCG slice of the Dev Fund
as a Restricted Fund donation", add:

> Funds that have accrued to Zcash Community Grants are protected as specified
> in ZIP [this ZIP]. They MUST NOT be reduced, redirected, burned or otherwise
> taken by any later ZIP, network upgrade, vote or agreement, and MUST be used
> only for the purposes described in this section. A later ZIP MAY change only
> the rate at which new funds accrue.

In the section "Transparency and Accountability", add to the list of
obligations:

> * Publication and annual update of a ten-year budget, treasury plan and
>   ZEC-depreciation hedging strategy, as specified in ZIP [this ZIP].

## Changes to ZIP 1016

In the section "Administrative obligations and constraints", after the first
paragraph, add:

> Funds received by Zcash Community Grants under this ZIP are Accrued ZCG
> Funds as defined in ZIP [this ZIP], and are protected as specified there.

## Security precautions

Nothing in this ZIP reduces the obligations in the "Security precautions"
section of ZIP 1016 [^zip-1016-security]. The Treasury Plan SHOULD strengthen
them.

## Testnet-specific considerations

This ZIP has no effect on Testnet. Testnet funds have no value and are not
Accrued ZCG Funds.


# Rationale

## Why freeze the past but not the future?

Emphasis on the past is deliberate. The community has a strong interest in
being able to change how much new issuance goes to grants, including to stop
it. It has a much weaker interest, and incurs serious costs, in being able to
reach back and take money that was issued for a stated purpose. Splitting the
two lets future funding debates focus on the future.

## Why restate ZIP 1015's permitted uses rather than invent new ones?

The goal is to protect the bargain under which the funds were issued, not to
change it. Restating ZIP 1015 keeps the ZCG Committee's existing discretion,
including over administration expenses, and avoids creating a new set of rules
that grantees would have to learn.

## Why allow treasury management?

A rule that accrued funds cannot be moved for any purpose other than grants,
read literally, could stop ZCG from converting ZEC to dollars to pay a
dollar-denominated grant, or from hedging. That would be the opposite of what
is intended. This ZIP treats any action that keeps the value inside the
restricted fund as treasury management, not as a transfer out of it, and asks
for the policy that governs it to be published.

## Why not require a coinholder-amount voting round to adopt this ZIP?

Neither ZIP 1015 nor ZIP 1016 gives coinholder votes any formal role over ZCG
funds. ZIP 1016 binds coinholder votes only to the Coinholder-Controlled Fund.
The ZCG Committee is selected by ZCAP. This ZIP therefore asks for both a
coinholder-amount voting round and a ZCAP poll as evidence of support, rather
than making either one alone the deciding vote. This also avoids implying that
a coinholder-amount voting round could later authorize a Taking.

## Why a deadline of 31 March 2027?

It gives ZCG about four and a half months from the drafting of this ZIP,
including a 30-day draft comment period, and means the first Treasury Plan
is in place well before the scheduled end of the ZCG funding stream in late
2028, and before any network upgrade that might change the Accrual Rate.


# Open questions

1. **Scope of "grants".** Should administration expenses (the Discretionary
   Budget and committee compensation) remain Permitted Uses, as in ZIP 1015,
   or should accrued funds be restricted to grants only? This draft keeps
   them, because ZIP 1015's definition of the ZCG program includes them and
   the program cannot run without them.
2. **Future grant-rule changes.** See the open question under
   [Only the Accrual Rate may change](#only-the-accrual-rate-may-change).
3. **Legal form.** Whether Cayman Islands law allows FPF to give an
   irrevocable restriction with an independent enforcer, and who that
   enforcer should be, needs advice from FPF's counsel.
4. **Voluntary transfers.** This draft forbids even a voluntary transfer of
   accrued funds to the NSM or a burn address, such as the voluntary taper
   that ZCG itself floated in October 2026. That is intended, but it should be
   stated clearly in any forum discussion.
5. **Adoption bar.** Whether to make approval in a coinholder-amount voting
   round and a ZCAP poll a hard requirement (MUST) rather than a SHOULD.


# References

[^BCP14]: [Information on BCP 14 — "RFC 2119: Key words for use in RFCs to Indicate Requirement Levels" and "RFC 8174: Ambiguity of Uppercase vs Lowercase in RFC 2119 Key Words"](https://www.rfc-editor.org/info/bcp14)

[^zip-0000]: [ZIP 0: ZIP Process](zip-0000.rst)

[^zip-0214]: [ZIP 214: Consensus rules for a Zcash Development Fund](zip-0214.rst)

[^zip-1015]: [ZIP 1015: Block Subsidy Allocation for Non-Direct Development Funding](zip-1015.rst)

[^zip-1015-zcg]: [ZIP 1015: Block Subsidy Allocation for Non-Direct Development Funding — Zcash Community Grants](zip-1015.rst#zcash-community-grants-zcg)

[^zip-1015-decentralization]: [ZIP 1015: Block Subsidy Allocation for Non-Direct Development Funding — Furthering Decentralization](zip-1015.rst#furthering-decentralization)

[^zip-1015-transparency]: [ZIP 1015: Block Subsidy Allocation for Non-Direct Development Funding — Transparency and Accountability](zip-1015.rst#transparency-and-accountability)

[^zip-1015-enforcement]: [ZIP 1015: Block Subsidy Allocation for Non-Direct Development Funding — Enforcement](zip-1015.rst#enforcement)

[^zip-1015-funding-streams]: [ZIP 1015: Block Subsidy Allocation for Non-Direct Development Funding — Funding Streams](zip-1015.rst#funding-streams)

[^zip-1016]: [ZIP 1016: Community and Coinholder Funding Model](zip-1016.md)

[^zip-1016-zcg]: [ZIP 1016: Community and Coinholder Funding Model — Zcash Community Grants](zip-1016.md#zcash-community-grants)

[^zip-1016-disbursement]: [ZIP 1016: Community and Coinholder Funding Model — Disbursement process](zip-1016.md#disbursement-process)

[^zip-1016-security]: [ZIP 1016: Community and Coinholder Funding Model — Security precautions](zip-1016.md#security-precautions)

[^zip-2008]: [ZIP 2008: Update to `FS_FPF_ZCG_H3` address list](zip-2008.md)
