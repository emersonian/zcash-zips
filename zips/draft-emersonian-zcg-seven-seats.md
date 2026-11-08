    ZIP: Unassigned
    Title: Update to ZIP 1015: Expand the ZCG Committee to Seven Seats
    Owners: Emerson <TBD>
    Status: Draft
    Category: Process
    Created: 2026-11-08
    License: MIT
    Discussions-To: <URL TBD>
    Updates: 1015


# Terminology

The key words "MUST", "MUST NOT", "SHALL", "SHOULD", and "MAY" in this document
are to be interpreted as described in BCP 14 [^BCP14] when, and only when, they
appear in all capitals.

The terms "Zcash Community Grants" (or "ZCG"), "ZCG Committee", "Financial
Privacy Foundation" (or "FPF"), "Zcash Community Advisory Panel" (or "ZCAP"),
and "Discretionary Budget" in this document are to be interpreted as defined or
used in ZIP 1015 [^zip-1015].

"ZEC" refers to the native currency of Zcash on Mainnet.

The terms below are to be interpreted as follows:

Member

: A person who holds a seat on the ZCG Committee.

Seated Members

: The Members holding a seat at a given time. A seat that is vacant is not
  counted.

Large Grant

: A grant, or an extension, renewal, or increase of a grant, whose total value
  over its full term is more than US$500,000, valued at the time of the
  decision. Grants to the same applicant for closely related work approved
  within a 90-day period are added together for this purpose.


# Abstract

This ZIP increases the ZCG Committee from five seats to seven.

The two new seats are filled by the same process that selects the existing
seats, in the next selection round after this ZIP becomes Active, and are
placed in the election cycles so that four seats and three seats come up for
selection at different times. The existing limits in ZIP 1015 on Members
associated with BP/ECC, ZF, and FPF are unchanged. With seven seats, those
limits mean that at least four Members have none of those associations.

The ZIP also sets a quorum of five Members, and requires at least four votes in
favor for any Large Grant, so that a decision worth more than US$500,000 is
always backed by a majority of the full Committee.

Committee compensation continues to be set by ZCAP and paid from the
Discretionary Budget. The ZIP has no significant privacy implications.


# Motivation

ZIP 1015 provides that "ZCG awards are subject to approval by a five-seat ZCG
Committee" [^zip-1015-zcg]. That size was carried over from the Major Grants
committee of ZIP 1014 [^zip-1014], when the amounts involved were much smaller
and ZCG's role was narrower. ZIP 1016 recognized this, noting that "Any
changes to the ZCG or its governance, such as its expansion to include more
members, may be desired but are specifically outside this proposal's scope"
[^zip-1016].

The ZCG funding stream is 8% of the block subsidy. At the current issuance
rate that is about 144 ZEC per day, or roughly 52,500 ZEC a year (8% of
1.5625 ZEC per 75-second block, or the equivalent at 25-second spacing). At
recent prices this is on the order of US$60 million a year, decided by five
people. These figures are the author's arithmetic and are given for scale only.

A five-seat Committee has several weaknesses at that scale:

* Recusal removes a large share of the Committee. ZIP 1015 requires Members to
  recuse when they have a financial interest. One recusal leaves four people,
  and two leave three, so a single conflicted decision can rest on a bare
  majority of a much smaller group.
* The association limits leave little room for independence. ZIP 1015 allows
  at most one Member associated with each of BP/ECC, ZF, and FPF
  [^zip-1015-zcg]. On a five-seat Committee, those three seats can form a
  majority on their own.
* A majority is easy to reach. Three people decide any question, and three
  people are a small target for pressure from applicants or other interests.
* Workload is concentrated. Five people review every grant, monitor
  milestones, and approve Discretionary Budget spending, which limits how
  carefully each application can be read.

Seven seats address these without changing how the Committee is selected or
what it does.


# Privacy Implications

This ZIP has no significant privacy implications. It changes the number of
seats on an existing public committee and its voting rules. The new Members
are selected and disclosed in the same way as current Members.


# Requirements

* The ZCG Committee has seven seats.
* The new seats are filled by the existing selection process, without
  interrupting the Committee's work.
* Seats continue to come up for selection on a staggered schedule.
* At least four Members have no association with BP/ECC, ZF, or FPF.
* No decision is made by fewer than five Members, and no Large Grant is
  approved with fewer than four votes in favor.
* The cost of the larger Committee stays within the existing Discretionary
  Budget process.


# Non-requirements

* This ZIP does not change who selects the ZCG Committee, the one-year term,
  the conflict-of-interest policy, or the association limits in ZIP 1015.
* This ZIP does not add a procedure for removing Members or filling
  mid-term vacancies. Those are left to other proposals.
* This ZIP does not change the ZCG funding stream or the uses of ZCG funds.


# Specification

## Number of seats

In item 5 of the section "Zcash Community Grants (ZCG)" of ZIP 1015
[^zip-1015-zcg], "a five-seat ZCG Committee" is replaced with "a seven-seat ZCG
Committee".

## Filling the new seats

The two new seats SHALL be filled by the ZF's Community Advisory Panel or
successor process, in the same way as the existing seats, at the first
selection round that opens at least 30 days after this ZIP becomes Active.
If no selection round is scheduled within 90 days after this ZIP becomes
Active, the selecting body SHOULD hold a special round for the new seats
within that period.

To keep elections staggered, the selecting body SHALL assign the seven seats
to two groups, one of four seats and one of three, whose selection rounds are
held at different times of the year. Where this requires one of the new seats
to be filled for a first term shorter or longer than one year, that first term
MAY be adjusted by up to six months. Every later term is one year, as in item
7 of the section "Zcash Community Grants (ZCG)" of ZIP 1015.

The selecting body SHALL publish the assignment of seats to groups, and the
dates of each group's selection round, on the Zcash Community Forum before the
new seats are filled.

Until the new seats are filled, the ZCG Committee continues to operate with
its existing Members, and the quorum and voting rules in this ZIP apply with
five in place of seven seats: the quorum is four, and a Large Grant requires
three votes in favor.

## Quorum and voting

A decision of the ZCG Committee MUST NOT be made unless at least five Members
who are not recused take part.

A decision is approved by a majority of the votes cast by Members who are not
recused.

A Large Grant MUST NOT be approved unless at least four Members vote in favor.

If recusals or vacancies mean that fewer than five Members are able to take
part in a decision, the decision MAY be made by all Members who are able to
take part, provided that there are at least four of them, and provided that a
Large Grant still receives at least four votes in favor. The ZCG Committee
MUST record in its published minutes when a decision is made under this
paragraph, and why.

The ZCG Committee MUST publish, for each grant decision, the number of Members
who voted in favor, against, and abstained, and the number who recused.

## Compensation

Compensation for the new seats SHALL be determined by ZCAP or successor
process, and paid from the Discretionary Budget, under item 9 of the section
"Zcash Community Grants (ZCG)" of ZIP 1015, in the same way as for the
existing seats. ZCAP SHOULD review the size of the Discretionary Budget to
take account of the additional seats.

## Changes to ZIP 1015

In the section "Zcash Community Grants (ZCG)" of ZIP 1015 [^zip-1015-zcg]:

* in item 5, "a five-seat ZCG Committee" is replaced with "a seven-seat ZCG
  Committee"; and
* at the end of item 5, the following is added:

> The ZCG Committee's quorum, voting rules, and the transition from five to
> seven seats are specified in ZIP [this ZIP].

## Effective date

This ZIP takes effect on the date its Status becomes Active.


# Rationale

## Why seven

Seven is the smallest odd number that leaves a clear independent majority
under the existing association limits: with at most three associated
Members, at least four are independent. It also means that one recusal still
leaves six Members, and two leave five, so a quorum can almost always be met.

Larger committees, such as nine or eleven, would further reduce the weight of
each Member, but would be harder to fill with qualified people each year, cost
more, and make discussion slower. Seven is a common size for grant and
investment committees that handle sums of this order.

## Why a four-vote floor for Large Grants

Under a simple majority of those voting, a Large Grant could pass with three
votes if several Members were recused or absent. Requiring four votes means
that every large decision is backed by a majority of the full Committee. The
US$500,000 threshold is meant to catch the grants that matter most to ZCG's
budget while leaving routine grants unaffected.

## Why keep the existing selection process

How the Committee is selected is a separate and more contested question. This
ZIP only changes its size, so that it can be adopted without settling that
question. It works with any selection process that ZIP 1015 or a later ZIP
specifies.

## Relationship to other drafts

This ZIP fits with the drafts that bar Members from applying for grants during
their term [^draft-grant-bar] and that move treasury decisions to a separate
Treasury Committee [^draft-zcg-treasury]. Neither depends on this one. If the
Treasury Committee draft is adopted, the grants committee will spend its time
on grant review, which makes the extra seats more useful.


# Open questions

* Is US$500,000 the right threshold for a Large Grant, and should it be set in
  ZEC instead?
* Should the quorum be five, or a majority of Seated Members?
* Should the new seats be reserved, at least initially, for people with no
  association with BP/ECC, ZF, FPF, or any current grantee?
* Should this ZIP also add a rule for filling a mid-term vacancy?


# References

[^BCP14]: [Information on BCP 14, "RFC 2119: Key words for use in RFCs to Indicate Requirement Levels" and "RFC 8174: Ambiguity of Uppercase vs Lowercase in RFC 2119 Key Words"](https://www.rfc-editor.org/info/bcp14)

[^zip-1014]: [ZIP 1014: Establishing a Dev Fund for ECC, ZF, and Major Grants](zip-1014.rst)

[^zip-1015]: [ZIP 1015: Block Subsidy Allocation for Non-Direct Development Funding](zip-1015.rst)

[^zip-1015-zcg]: [ZIP 1015: Block Subsidy Allocation for Non-Direct Development Funding, Zcash Community Grants](zip-1015.rst#zcash-community-grants-zcg)

[^zip-1016]: [ZIP 1016: Community and Coinholder Funding Model](zip-1016.md)

[^draft-grant-bar]: [Draft ZIP: Update to ZIP 1015: ZCG Committee Members May Not Apply for Grants During Their Term](draft-emersonian-zcg-member-grant-bar.md)

[^draft-zcg-treasury]: [Draft ZIP: ZCG Treasury Committee, Budget, and Hedging Plan](draft-emersonian-zcg-treasury-committee.md)
