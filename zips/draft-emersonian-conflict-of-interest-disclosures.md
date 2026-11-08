    ZIP: Unassigned
    Title: Quarterly Conflict-of-Interest Disclosures by Key-Holder Organizations and ZIP Editors
    Owners: Emerson <@emersonian>
    Status: Draft
    Category: Process
    Created: 2026-11-08
    License: MIT
    Discussions-To: <URL TBD>
    Updates: 0, 1016


# Terminology

The key words "MUST", "MUST NOT", "SHALL", "SHOULD", "SHOULD NOT", and "MAY"
in this document are to be interpreted as described in BCP 14 [^BCP14] when,
and only when, they appear in all capitals.

The terms "Zcash Community Grants" (or "ZCG"), "ZCG Committee", and
"Financial Privacy Foundation" (or "FPF") in this document are to be
interpreted as defined in ZIP 1015 [^zip-1015].

The terms "Coinholder-Controlled Fund" and "Key-Holder Organizations" in this
document are to be interpreted as described in ZIP 1016 [^zip-1016], as
amended by any ZIP that updates the membership of the Key-Holder
Organizations (see for example [^draft-mcgee-keyholders]). At the time of
writing, the Key-Holder Organizations are expected to be Zcash Foundation,
Shielded Labs, and Zcash Open Development Lab.

The term "ZIP Editor" is to be interpreted as described in ZIP 0
[^zip-0000-editors].

"Zcash Community Forum" (or "the Forum") means the discussion forum hosted at
<https://forum.zcashcommunity.com/>, or any successor designated by a ZIP
(see for example the Zcash Town Square proposal [^draft-town-square]).

"ZEC" refers to the native currency of Zcash on Mainnet.

The terms below are to be interpreted as follows:

Coinholder-amount voting round

: A coinholder vote held under ZIP 1016 [^zip-1016-disbursement], in which each
  ballot is weighted by the amount of ZEC that the voter proves control of,
  conducted under the rules for such votes that are in effect at the time the
  vote is held.

Disclosure Quarter

: A calendar quarter: 1 January to 31 March, 1 April to 30 June, 1 July to 30
  September, or 1 October to 31 December (all dates in UTC).

Covered Organization

: Each of the following:

  * each Key-Holder Organization; and
  * each Editor Employer, meaning each organization that employs or engages
    a ZIP Editor (as an employee, officer, director, contractor, or consultant
    on a regular basis), or with which a ZIP Editor is listed as associated in
    ZIP 0, whether or not that ZIP Editor acts as an Editor "in their
    individual capacity". For example, at the time of writing this includes
    Zcash Foundation, Shielded Labs, Project Tachyon, Valar Group, and Zcash Open
    Development Lab.

Covered Individual

: Each of the following:

  * each ZIP Editor; and
  * each person who, for a Key-Holder Organization, holds or controls a key to
    any multisig or other address that holds Coinholder-Controlled Fund assets,
    or who takes part in any decision that ZIP 1016 assigns to the Key-Holder
    Organizations (including the grant application process, veto declarations,
    determinations of whether proposals are in competition, the organization of
    coinholder-amount voting rounds, the certification of their results, and
    the signing of disbursements); and
  * each director and officer of a Key-Holder Organization.

Covered Party

: A Covered Organization or a Covered Individual.

Hold

: To Hold ZEC means to have beneficial ownership of it, or to have the
  authority (alone or with others) to spend it or to vote it in a
  coinholder-amount voting round, whether directly or through a custodian,
  exchange, fund, trust, exchange-traded product, affiliate, or any other
  intermediary. A person who controls an entity Holds the ZEC that the entity
  Holds.

Coinholder

: Any person or entity that Holds any amount of ZEC.

Reference Price

: The Reference Price for a day is the ZEC/USD daily closing price for that day
  published by the price source that the Key-Holder Organizations jointly
  designate on the Forum for the purposes of this ZIP. Until they do so, it is
  the daily closing price published by CoinGecko.

Significant Coinholder

: A Coinholder that, at any time during the relevant Disclosure Quarter, Holds
  ZEC with a value greater than US$1,000,000 at the Reference Price for that
  day.

Suspected

: A Coinholder or Significant Coinholder is Suspected if the Covered Party
  does not know that it is one, but has reasonable grounds to believe that it
  is one, for example because of public reporting, public filings, on-chain
  analysis that the Covered Party is aware of, statements made by the person or
  entity or by people close to it, or the Covered Party's own observations.

Investment

: Any equity, convertible instrument (for example a SAFE or convertible note),
  token warrant, option, loan, revenue share, or other financial interest in a
  Covered Organization, or any donation or grant to it of more than US$10,000 in
  a twelve-month period, whether made in fiat currency, ZEC, or any other asset.

Investor

: An Investor in a Covered Organization is any person or entity that holds, or
  within the previous 24 months held, an Investment in that Covered
  Organization, or that has entered into a binding commitment to make one.

Coinholder Investor

: An Investor that is a Coinholder (known or Suspected), of any amount.

Affiliation

: An Affiliation between a Covered Party and another person or entity is any of
  the following relationships, existing at any time during the relevant
  Disclosure Quarter:

  * an immediate family relationship (spouse, domestic partner, parent, child,
    sibling, or any of these by marriage);
  * employment, a consulting or advisory engagement, or a board or officer
    position, in either direction;
  * a business partnership, joint venture, co-investment, or shared financial
    interest of more than US$10,000;
  * receipt of gifts, hospitality, loans, or payments of more than US$1,000 in
    aggregate during the previous twelve months, in either direction;
  * any agreement or understanding (formal or informal) about how either party
    will act in relation to a coinholder-amount voting round, the
    Coinholder-Controlled Fund, ZCG, or the ZIP Process; or
  * a close personal relationship that a reasonable member of the Zcash
    community, knowing of it, would consider likely to influence the Covered
    Party's judgment in its role.

Coinholder Affiliate

: A Coinholder Affiliate of a Covered Party is any Significant Coinholder (known
  or Suspected) with which the Covered Party has an Affiliation. For a Covered
  Individual, this includes Affiliations of the individual's immediate family
  members, to the extent known to the individual.

Reportable Relationship

: Any relationship described in [Reportable
  relationships](#reportable-relationships).

Disclosed Party

: A person or entity named (or, under [Protected Persons](#protected-persons),
  identified by label) in a Disclosure Statement.

Applicable Conflict-of-Interest Policy

: Defined in [Applicable Conflict-of-Interest
  Policy](#applicable-conflict-of-interest-policy).

Policy Notice

: The document described in [Policy Notice](#policy-notice).

Investor Acknowledgment

: A signed statement described in [Investor
  Acknowledgments](#investor-acknowledgments).

Effective Date

: The first day of the first Disclosure Quarter that begins at least 30 days
  after this ZIP reaches Active status.


# Abstract

This ZIP requires each Key-Holder Organization, each ZIP Editor, each
organization that employs a ZIP Editor, and the individuals who act for the
Key-Holder Organizations, to publish a signed conflict-of-interest disclosure
on the Zcash Community Forum every quarter.

Each disclosure must list every known or suspected ZEC coinholder that has
made an equity or other investment in the disclosing organization, and every
personal or business affiliation with any person or entity that holds, or is
suspected of holding, more than US$1 million in ZEC. It must also cover other
potential conflicts relating to coinholder-amount voting rounds, the
Coinholder-Controlled Fund, and the ZIP Process.

For each coinholder investor, the disclosing party must verify that the
investor is aware of the existing conflict-of-interest provisions that apply
to coinholder votes (the ZCG recusal policy in ZIP 1015, as carried into
ZIP 1016), and must publish on the Forum a signed acknowledgment from that
investor proving it.

The ZIP sets out cure periods and consequences for non-compliance: a
non-compliant Key-Holder Organization loses its discretionary powers under
ZIP 1016 (while remaining obliged to sign approved disbursements), and a
non-compliant ZIP Editor is suspended and then removed. It updates ZIP 0 and
ZIP 1016 accordingly.

To protect people from theft and physical risk, disclosures never state the
size of anyone's holdings, and private individuals can be listed under a
stable label instead of their name.


# Motivation

The Key-Holder Organizations hold the keys to the Coinholder-Controlled Fund
and make every discretionary decision around it. Under ZIP 1016 they run the
grant application process, decide whether proposals are in competition, can
veto grants on principled grounds, and decide whether to sign disbursements.
The ZIP Editors decide which ZIPs are accepted, how they are worded, and when
they change status, including ZIPs that set the rules for coinholder-amount
voting rounds and for the Coinholder-Controlled Fund itself.

Both groups are funded, employed, or invested in by people and entities that
may themselves vote in coinholder-amount voting rounds. In a vote weighted by
the amount of ZEC held, a small number of large holders can decide the
outcome on their own. At the time of writing, single entities have been
publicly reported to hold more ZEC than the entire 420,000 ZEC quorum
required by ZIP 1016 [^zip-1016-disbursement]. Development organizations
that serve as Key-Holder Organizations or employ ZIP Editors have raised
outside capital (for example, Zcash Open Development Lab announced
US$25 million in seed funding in March 2026 [^draft-mcgee-keyholders]), and
the identity of those investors, and whether they hold ZEC, has not been
systematically disclosed.

The existing conflict-of-interest provisions are not enough to address this:

* ZIP 1015 requires the ZCG Committee to recuse when it has a financial
  interest in a proposal, and limits how many Committee members may be
  associated with any one organization [^zip-1015-zcg]. ZIP 1016 applies
  those provisions to the Key-Holder Organizations' administration of the
  Coinholder-Controlled Fund "with coinholder voting replacing the role of
  the ZCG Committee" [^zip-1016-admin]. But recusal depends on knowing who has
  an interest, and nothing requires the relevant relationships to be
  disclosed.
* ZIP 1016 also states that "No organizations or individuals are restricted
  from voting their coins" [^zip-1016-disbursement]. Read together with the
  provision above, it is unclear whether a coinholder with a financial
  interest in a proposal is expected to refrain from voting on it. Investors
  in the organizations that run the process are entitled to know about this
  provision and about the community's expectations, and the community is
  entitled to know that they know.
* ZIP 0 requires ZIP Editors to "declare any potential or perceived conflict
  of interest" [^zip-0000-editors], but sets no schedule, no scope, no
  diligence standard, and no consequence for failing to do so. In practice,
  the declarations in ZIP 0 describe Editors' roles, not their funders or
  their relationships with large holders.

Quarterly, structured, signed disclosure, posted where the community already
discusses governance, lets coinholders, grant applicants, and the wider
community judge for themselves whether a decision may have been influenced.
Requiring investors to acknowledge the policy in writing removes any later
claim that they were unaware of it.


# Privacy Implications

Publishing that a named private individual holds more than US$1 million in
ZEC would make that person a target for theft, extortion, and physical
attack. This ZIP therefore:

* never requires the amount of any Disclosed Party's holdings to be
  published, only whether the relevant threshold is (known or Suspected to
  be) exceeded;
* allows private individuals to be identified by a stable label rather than
  by name, with their identity verified confidentially by Disclosure
  Reviewers (see [Protected Persons](#protected-persons));
* requires entities (companies, funds, trusts, DAOs, and so on) and public
  figures to be named, since the community's interest in knowing who funds
  the governance process outweighs their interest in anonymity; and
* prohibits publishing home addresses, personal contact details, wallet
  addresses, or other information that would help someone locate a Disclosed
  Party or their funds, except where the Disclosed Party has itself chosen to
  sign with a Zcash address under
  [Signature methods](#signature-methods).

Investors who are unwilling to be named have the option of not investing in,
or not continuing to fund, organizations that hold governance roles in Zcash.
This is an intended consequence: anonymity is not compatible with a funding
relationship to the people who run the coinholder-amount voting process.


# Requirements

* Every Key-Holder Organization, ZIP Editor, and Editor Employer publishes a
  conflict-of-interest disclosure on the Forum every quarter, including when
  it has nothing to disclose.
* Disclosures cover both the organizations and the individuals who act for
  them.
* Disclosures name every known or suspected coinholder that has invested in a
  Covered Organization, and every affiliation with a known or suspected holder
  of more than US$1 million in ZEC.
* For each coinholder investor, a signed, publicly verifiable proof that the
  investor is aware of the Applicable Conflict-of-Interest Policy is
  published on the Forum.
* Failure to comply has defined, proportionate consequences that do not put
  Coinholder-Controlled Fund assets or approved grantees at risk.
* Disclosures do not create new physical-safety risks for private individuals
  by publishing their holdings.


# Non-requirements

* This ZIP does not prohibit any relationship, investment, or holding. It
  requires disclosure, not divestment.
* This ZIP does not resolve whether ZIP 1016 requires coinholders with a
  financial interest in a proposal to refrain from voting. It requires that
  investors be made aware of the relevant text and of the fact that it is
  disputed.
* This ZIP does not impose recusal obligations on ZIP Editors beyond those in
  ZIP 0, except while an Editor is suspended under this ZIP.
* This ZIP does not cover the ZCG Committee or FPF, which are subject to
  ZIP 1015. Extending the same disclosures to them is left to a future ZIP.
* Publication of Key-Holder Organizations' bylaws, governing documents, and
  the legal agreement required by ZIP 1016 is addressed by a companion
  proposal on Key-Holder Organization accountability [^companion-kho], not by
  this ZIP. This ZIP is intended to stand alone, and does not depend on that
  proposal being adopted.
* This ZIP does not change any consensus rule.


# Specification

## Applicable Conflict-of-Interest Policy

The Applicable Conflict-of-Interest Policy, for a Covered Party, consists of
the following, as in effect at the date of the Policy Notice:

1. ZIP 1015, section "Zcash Community Grants (ZCG)", point 7 [^zip-1015-zcg],
   including the definition of "Association" and the FPF Board policy it
   refers to, to the extent FPF has published it;
2. ZIP 1016, sections "Administrative obligations and constraints"
   [^zip-1016-admin] and "Disbursement process" [^zip-1016-disbursement],
   including the statement that "No organizations or individuals are
   restricted from voting their coins";
3. for ZIP Editors and Editor Employers, ZIP 0, section "ZIP Editors"
   [^zip-0000-editors];
4. any written conflict-of-interest policy of the Covered Organization, or,
   for a Covered Individual, of each Covered Organization for which they act;
   and
5. this ZIP.

Each Covered Organization MUST publish its written conflict-of-interest
policy, if it has one, with its first Disclosure Statement and within 14 days
of any amendment. One that has no written policy MUST say so in each
Disclosure Statement.

## Reportable relationships

Each Covered Party MUST disclose the following Reportable Relationships.

### Coinholder Investors

Each Covered Organization MUST disclose every Coinholder Investor in it,
whether the Investor is known to be a Coinholder or is Suspected of being
one, and regardless of the amount of ZEC the Investor Holds.

For each Coinholder Investor, the disclosure MUST state:

* the Investor's legal name (subject to
  [Protected Persons](#protected-persons));
* the type of Investment (for example "Series A preferred equity", "SAFE",
  "donation");
* the date of the Investment, or of the first Investment if there are
  several;
* the size of the Investment, in one of the following bands: under
  US$100,000; US$100,000 to US$1,000,000; US$1,000,000 to US$10,000,000; over
  US$10,000,000;
* whether the Investor holds any board seat, observer right, veto, or
  information right in the Covered Organization;
* whether the Investor is known or Suspected to be a Coinholder, and whether
  it is known or Suspected to be a Significant Coinholder, with a short
  statement of the basis for any suspicion; and
* the status of the Investor's Investor Acknowledgment (obtained, pending, or
  refused).

A Covered Individual who personally holds an Investment in a Covered
Organization for which they act, or in any entity that is an Investor in such
a Covered Organization, MUST also disclose that.

### Coinholder Affiliates

Each Covered Party MUST disclose every Coinholder Affiliate, whether known or
Suspected.

For each Coinholder Affiliate, the disclosure MUST state:

* the Coinholder Affiliate's name (subject to
  [Protected Persons](#protected-persons));
* which Covered Party has the Affiliation (the organization, or which
  individual);
* the type of Affiliation, using the categories in the definition of
  Affiliation;
* when the Affiliation began, and if it has ended, when; and
* whether the Coinholder Affiliate is known or Suspected to be a Significant
  Coinholder, with a short statement of the basis for any suspicion.

### Other potential conflicts

Each Covered Party MUST also disclose any other relationship, interest, or
circumstance that a reasonable member of the Zcash community would consider a
potential conflict of interest in relation to the Covered Party's role,
including at least:

* any financial interest (including employment, contracts, grants, or equity)
  in any applicant for, or beneficiary of, a grant that has been or is
  scheduled to be put to a coinholder-amount voting round, or that is before
  the ZCG Committee;
* any financial or employment interest in, or maintainer role for, a Zcash
  consensus node implementation, wallet, exchange, custodian, or other
  product or service whose interests could be materially affected by a ZIP
  or by a Coinholder-Controlled Fund decision;
* for a Covered Individual, whether they are themselves a Significant
  Coinholder (yes or no, without stating any amount); and
* any external influence or constraint placed or attempted to be placed on
  the Covered Party's actions in its role, to the extent already required to
  be disclosed by ZIP 0 [^zip-0000-editors] or not otherwise disclosed.

## Diligence

A Covered Party MUST make reasonable inquiry to identify its Reportable
Relationships. At a minimum:

* each Covered Organization MUST, at least once in each twelve-month period
  and before accepting any new Investment, ask each of its Investors in
  writing whether the Investor Holds ZEC and whether it is a Significant
  Coinholder;
* an Investor that does not answer within 30 days, or declines to answer,
  MUST be treated as a Suspected Coinholder and disclosed as such, with the
  basis stated as "declined to state" or "did not respond";
* each Covered Organization MUST ask each of its Covered Individuals, before
  each Disclosure Statement, to identify their Reportable Relationships, and
  MUST include them; and
* a Covered Party MUST NOT avoid knowledge of a Reportable Relationship (for
  example by instructing others not to tell it). A Covered Party that has
  deliberately avoided knowledge of a relationship is treated as knowing of
  it.

## Disclosure Statements

### Timing

Each Covered Party MUST publish:

* an "Initial Disclosure Statement" within 30 days after the Effective
  Date, or, for a person or organization that becomes a Covered Party after
  the Effective Date, before it first acts in its role (for example, before a
  new ZIP Editor first takes part in an Editor decision);
* a "Quarterly Disclosure Statement" no later than the 21st day after the
  end of each Disclosure Quarter, covering that Disclosure Quarter; and
* an "Interim Disclosure Statement" within 14 days after it becomes aware
  of any new Reportable Relationship, or of any material change to a
  disclosed one, that is not already disclosed.

In addition, no later than 7 days before the voting period of each
coinholder-amount voting round opens, each Key-Holder Organization MUST
publish a short "Pre-Vote Confirmation" that its most recent Disclosure
Statement, and those of its Covered Individuals, are complete and current,
or publish an Interim Disclosure Statement correcting them.

A Covered Organization MAY publish a single Disclosure Statement that also
covers its Covered Individuals, provided that each Covered Individual signs
it as described below.

A Disclosure Statement MUST be published even if the Covered Party has no
Reportable Relationships, in which case it MUST say so explicitly.

### Place of publication

Every document this ZIP requires to be published MUST be posted on the Forum,
in one thread per Covered Organization titled "Conflict-of-Interest Register:
[Organization name]", or, for a ZIP Editor with no Editor Employer, "[Editor
name]". The Forum version is authoritative.

A published Disclosure Statement MUST NOT be deleted, and MUST NOT be edited
except to add a clearly marked correction. A correction that adds or removes a
Reportable Relationship MUST be made by a new post. Where the Zcash Town Square
ZIP [^draft-town-square] is in effect, its rules on edits and deletions also
apply.

### Contents

Each Disclosure Statement MUST include:

1. the name of the Covered Organization and each Covered Individual it
   covers, and their roles;
2. the Disclosure Quarter (or, for an Interim Disclosure Statement, the date)
   it covers;
3. all Reportable Relationships, in the form specified in
   [Reportable relationships](#reportable-relationships), with any changes
   since the previous Disclosure Statement clearly marked;
4. a table summarizing, for each Disclosed Party that requires an Investor
   Acknowledgment, its status and a link to the published acknowledgment;
5. a link to the Covered Organization's written conflict-of-interest policy,
   or a statement that it has none;
6. a description of any recusal made during the period by any Covered
   Individual because of a disclosed relationship;
7. the following certification:

   > I certify that, to the best of my knowledge after the reasonable inquiry
   > required by ZIP [XXX], this statement discloses every Reportable
   > Relationship of the Covered Parties it covers, and that nothing material
   > has been omitted.

8. the signatures of an officer of the Covered Organization and of each
   Covered Individual covered by the statement, using any method in
   [Signature methods](#signature-methods).

## Investor Acknowledgments

### Who must acknowledge

Each Covered Organization MUST obtain an Investor Acknowledgment from every
Coinholder Investor that it discloses (known or Suspected), and publish it on
the Forum.

Each Covered Party SHOULD also obtain and publish an Investor Acknowledgment
from each Coinholder Affiliate that is not an immediate family member.

### Policy Notice

Before requesting an Investor Acknowledgment, the Covered Organization MUST
send the Disclosed Party a Policy Notice, and MUST publish the same Policy
Notice on the Forum. A Policy Notice MUST:

* quote verbatim each of the provisions listed in items 1 to 3 of
  [Applicable Conflict-of-Interest Policy](#applicable-conflict-of-interest-policy)
  that apply to the Covered Party, and attach or link items 4 and 5;
* explain, in plain language, that ZIP 1016 applies the ZCG recusal policy
  to the administration of the Coinholder-Controlled Fund "with coinholder
  voting replacing the role of the ZCG Committee", that this has been read
  by some members of the community as an expectation that coinholders with a
  financial interest in a proposal refrain from voting on it, that ZIP 1016
  also states that no one is restricted from voting their coins, and that
  this question is unresolved;
* state that the Disclosed Party's relationship with the Covered Party will
  be published on the Forum each quarter for as long as it lasts;
* state that the Covered Party and its Covered Individuals are required to
  recuse themselves from decisions in which they have a financial interest,
  and that the Disclosed Party must not ask or encourage them to act contrary
  to the Applicable Conflict-of-Interest Policy; and
* carry a date and a SHA-256 hash of its own contents, by which Investor
  Acknowledgments will refer to it.

### Form of acknowledgment

An Investor Acknowledgment MUST be in the following form, completed and
signed by the Disclosed Party (or, for an entity, by a person authorized to
bind it):

> **Zcash Conflict-of-Interest Acknowledgment**
>
> Covered Party: [name of Covered Organization or Covered Individual]
>
> Acknowledging Party: [legal name, jurisdiction, and, for an entity, the
> name and title of the signatory]
>
> Relationship: [type of Investment or Affiliation, as disclosed]
>
> Policy Notice: dated [date], SHA-256 [hash]
>
> The Acknowledging Party confirms that:
>
> 1. it has received and read the Policy Notice identified above, including
>    the verbatim text of the conflict-of-interest provisions of ZIP 1015,
>    ZIP 1016, and (where applicable) ZIP 0 that it quotes;
> 2. it understands that the Covered Party has disclosed, and will continue
>    to disclose each quarter on the Zcash Community Forum, its relationship
>    with the Acknowledging Party;
> 3. it understands that the Covered Party and its Covered Individuals are
>    required to recuse themselves from decisions in which they have a
>    financial interest, and it will not ask or encourage them to act
>    contrary to that policy;
> 4. it understands that, if it votes in a coinholder-amount voting round,
>    its relationship with the Covered Party is public and may be taken into
>    account by the community, and that whether ZIP 1016 expects coinholders
>    with a financial interest in a proposal to refrain from voting on it is
>    currently disputed; and
> 5. its coinholder status is: [Holds ZEC worth more than US$1,000,000 /
>    Holds ZEC worth US$1,000,000 or less / Does not hold ZEC / Declines to
>    state].
>
> [Optional: The Acknowledging Party voluntarily commits to refrain from
> voting in any coinholder-amount voting round on a proposal in which the
> Covered Party has a financial interest.]
>
> Signed: [signature] Date: [date]

The Acknowledging Party MAY add further statements, but MUST NOT remove or
alter items 1 to 5. The optional commitment is voluntary and its absence is
not a breach of this ZIP.

### Signature methods

A Disclosure Statement or Investor Acknowledgment MUST be signed in a way that
any member of the community can verify, and the published post MUST say how to
verify it. Acceptable methods are:

1. an OpenPGP or SSH signature by a key verifiably linked to the signer (for
   example, published on the signer's website or in an earlier signed Forum
   post);
2. an electronic signature service, with the signed PDF and its certificate of
   completion both published; or
3. a post from the signer's own Forum account, quoting the full text, where
   the account is verifiably linked to the signer.

A signer MAY also sign with a Zcash address under ZIP 304 [^zip-0304] as
evidence that it Holds ZEC. Nothing in this ZIP requires anyone to reveal an
address.

### Timing of acknowledgments

An Investor Acknowledgment MUST be published within 45 days after the
Investor is first disclosed, or within 30 days for an Investment made after
the Effective Date. For new Investments, the Covered Organization SHOULD make
a signed acknowledgment a condition of closing. A fresh acknowledgment MUST be
obtained at least once every twelve months, and within 60 days after any
material amendment to the Applicable Conflict-of-Interest Policy.

### Refusal or non-response

If a Disclosed Party refuses to sign, or does not sign in time, the Covered
Organization MUST:

1. publish evidence that the Policy Notice was delivered (a "Proof of
   Delivery"), such as a delivery receipt or an email with full headers,
   redacted only of personal contact details;
2. mark the Disclosed Party as "Unacknowledged" in every later Disclosure
   Statement while the relationship lasts; and
3. send the Policy Notice and request the acknowledgment again at least once
   each Disclosure Quarter.

While a Disclosed Party is Unacknowledged, the Covered Organization's Covered
Individuals MUST recuse from any decision under ZIP 1016 or ZIP 0 concerning a
grant, proposal, or ZIP in which that party is known to have a financial
interest.

A Covered Organization that does all of this is not in breach of this ZIP
solely because a Disclosed Party refuses to sign. One that does not is
Non-Compliant.

## Protected Persons

A Disclosed Party is a "Protected Person" if it is a natural person who is
not a public figure, and who is (or is Suspected to be) a Significant
Coinholder. A person is a public figure for this purpose if they have publicly
stated a holding that would make them a Significant Coinholder, or hold an
officer or director position in a Covered Organization or in an entity that is
a Disclosed Party. Entities are never Protected Persons.

For a Protected Person, the Covered Party MAY publish a stable label of the
form `[Organization]-PP-[number]` instead of the person's name, together with
all other required information and a salted SHA-256 hash of the signed
Investor Acknowledgment. It MUST then deliver the person's identity, the
signed acknowledgment, and the salt confidentially to each Disclosure
Reviewer.

The "Disclosure Reviewers" are:

* for a Key-Holder Organization or its Covered Individuals, each other
  Key-Holder Organization; and
* for a ZIP Editor or Editor Employer, two ZIP Editors not associated with the
  same Editor Employer, chosen by the ZIP Editors, and each Key-Holder
  Organization other than the Editor Employer.

Within 30 days, each Disclosure Reviewer MUST publish a signed statement
confirming that the hash matches and the relationship appears accurate, or
saying why it cannot. Disclosure Reviewers MUST keep the information
confidential and use it for no other purpose.

## Enforcement

### Compliance status

At any time, each Covered Party is Compliant, In Cure, or Non-Compliant.

* A Covered Party that misses a deadline under this ZIP is "In Cure" for 14
  days after that deadline.
* A Covered Party that has not met the requirement by the end of that
  period becomes "Non-Compliant", and remains so until the requirement is
  met.
* A Covered Party that is the subject of a Material Omission Finding (below)
  becomes Non-Compliant immediately, and remains so until it has published a
  corrected Disclosure Statement and at least one further complete Quarterly
  Disclosure Statement on time.

A Covered Organization is Non-Compliant if any of its Covered Individuals is
Non-Compliant, unless that individual has been removed from all roles that
make them a Covered Individual.

Any person MAY post a notice on the Forum, in the relevant
Conflict-of-Interest Register thread, that a Covered Party appears to have
missed a deadline. Missing a deadline is an objective fact: no finding is
needed to start the cure period.

### Material Omission Findings

A "Material Omission" is an omission or misstatement of a Reportable
Relationship that the Covered Party knew of, or would have known of had it
made the inquiry required by [Diligence](#diligence). If it was deliberately
concealed, it is a "Knowing Misstatement".

A Material Omission is established (a "Material Omission Finding") if the
Covered Party admits it, or if a signed finding is published on the Forum:

* for a Key-Holder Organization or its Covered Individuals, by every other
  Key-Holder Organization; or
* for a ZIP Editor or Editor Employer, by a consensus of the other ZIP Editors
  (excluding those associated with the same Editor Employer), or by every
  Key-Holder Organization not associated with the subject.

The subject MUST be given at least 14 days' notice on the Forum and the chance
to respond publicly before a finding is published. A finding of a Knowing
Misstatement MUST say so.

### Consequences for Key-Holder Organizations

While a Key-Holder Organization is Non-Compliant:

1. it MUST NOT make a declaration of principled objection under the ZIP 1016
   Veto process, and any such declaration it has made that has not yet led
   to a veto does not count toward the two Key-Holder Organizations required.
   It MAY still declare that funding a grant would violate its legal or
   reporting obligations, but MUST publish the legal basis for that
   declaration;
2. it MUST NOT take part in determining whether grant proposals are in
   competition, in changing the grant application process, or in certifying
   the result of a coinholder-amount voting round; these decisions are taken
   by the other Key-Holder Organizations;
3. it remains bound to sign transactions for grants approved in
   coinholder-amount voting rounds, and to perform all of its security
   obligations under ZIP 1016. Non-compliance never excuses a failure to sign
   an approved disbursement;
4. it, and any organization in which any of its Covered Individuals has a
   financial interest, MUST NOT receive any new grant from the
   Coinholder-Controlled Fund, and the ZCG Committee SHOULD NOT award it any
   new grant. Payments under grants approved before it became Non-Compliant
   continue; and
5. the Key-Holder Organizations MUST state its Non-Compliant status in the
   published materials for every coinholder-amount voting round, next to every
   proposal in which it or its Covered Individuals have a financial interest.

If a Key-Holder Organization is Non-Compliant for any part of two
consecutive Disclosure Quarters, or is the subject of a finding of Knowing
Misstatement, the other Key-Holder Organizations MUST include in the next
coinholder-amount voting round a question asking whether coinholders support
replacing that Key-Holder Organization by a ZIP updating ZIP 1016, and MUST
publish the result. The result is advisory until such a ZIP is adopted. If a
ZIP establishing a procedure for replacing Key-Holder Organizations is in
effect (see for example [^companion-kho]), that procedure applies instead.

### Consequences for ZIP Editors and Editor Employers

While a ZIP Editor is Non-Compliant, or an Editor Employer with which the ZIP
Editor is associated is Non-Compliant, the ZIP Editor is "Suspended". A
Suspended ZIP Editor:

* MUST NOT take part in any decision that ZIP 0 assigns to the ZIP Editors,
  including assigning ZIP numbers, status changes, merging pull requests,
  rejections, and selecting or removing Editors;
* is not counted when determining whether the ZIP Editors have reached
  consensus; and
* MAY continue to handle the responsible disclosure of security
  vulnerabilities, and MAY comment on ZIPs in the same way as any other
  member of the community.

A ZIP Editor is removed from the role of ZIP Editor if:

* they have been Suspended for 60 consecutive days; or
* they, or an Editor Employer with which they are associated, are the
  subject of a finding of Knowing Misstatement.

The remaining ZIP Editors MUST update the list of ZIP Editors in ZIP 0 within
7 days of a removal. A removed ZIP Editor MAY be selected again under the
usual process in ZIP 0, but not until they (and their Editor Employer) have
published complete Disclosure Statements on time for at least one full
Disclosure Quarter after the removal.

If a suspension or removal would leave no ZIP Editor associated with the
Zcash Foundation, the requirement in ZIP 0 that there be at least one such
Editor is temporarily unmet, and the Zcash Foundation SHOULD nominate a
replacement promptly. A suspension or removal under this ZIP is not
prevented by that requirement.

### Legal agreement

Within 90 days after the Effective Date, the Key-Holder Organizations MUST
amend the legal agreement required by ZIP 1016 [^zip-1016] to bind each of
them to comply with this ZIP, and MUST publish on the Forum a signed
statement that they have done so.

### Compliance reporting

Each Key-Holder Organization MUST state its compliance status, and that of its
Covered Individuals, in each quarterly report it publishes on the
Coinholder-Controlled Fund.

The Key-Holder Organizations MUST jointly keep an index thread on the Forum,
titled "Conflict-of-Interest Register: Index", listing every Covered Party,
its register thread, the date of its latest Disclosure Statement, and its
compliance status, updated within 7 days of any change.

## Changes to ZIP 0

In the section "ZIP Editors", after the paragraph:

> ZIP Editors MUST declare any potential or perceived conflict of interest
> they have relating to their responsibilities as ZIP Editors.

the following paragraphs are added:

> In addition, each ZIP Editor, and each organization that employs or
> engages a ZIP Editor or with which a ZIP Editor is listed above as
> associated, MUST publish the quarterly conflict-of-interest disclosures,
> and obtain and publish the investor acknowledgments, required by
> ZIP [XXX]. A ZIP Editor who is Suspended under ZIP [XXX] MUST NOT take part
> in, and is not counted toward, any decision of the ZIP Editors. A ZIP
> Editor who is removed under ZIP [XXX] ceases to be a ZIP Editor.
>
> A person selected as an additional ZIP Editor MUST publish an Initial
> Disclosure Statement under ZIP [XXX] before first taking part in any
> decision of the ZIP Editors.

## Changes to ZIP 1016

In the section "Veto process", after the list of conditions under which a
grant is vetoed, the following paragraph is added:

> A Key-Holder Organization that is Non-Compliant under ZIP [XXX] cannot make
> a declaration of principled objection, and is not counted toward the two
> Key-Holder Organizations required for one.

In the section "Administrative obligations and constraints", after the
paragraph beginning "The provisions after the first paragraph of the section
'Zcash Community Grants (ZCG)'", the following paragraph is added:

> The Key-Holder Organizations, and the individuals who act for them, MUST
> publish the quarterly conflict-of-interest disclosures, and obtain and
> publish the investor acknowledgments, required by ZIP [XXX], and are
> subject to the consequences of non-compliance set out in that ZIP. The
> legal agreement required by the section "Requirements on use of the
> Coinholder-Controlled Fund" MUST bind them to comply with ZIP [XXX].


# Rationale

## Why quarterly

ZIP 1016 holds coinholder-amount voting rounds every three months, and
Key-Holder Organizations already report quarterly. A quarterly cycle, plus
Interim Disclosure Statements for new relationships and a Pre-Vote
Confirmation before each round, means the community always has current
information when it votes, without requiring continuous reporting.

## Why any amount for investors, but US$1 million for affiliations

An investor in a Covered Organization already has a direct interest in
decisions that affect it. If it holds any ZEC, it can vote in a round that
funds or harms the organization it invested in, so the size of its holding
does not matter.

Personal and business affiliations are far more numerous, and most involve
people whose holdings could not affect a vote. The US$1 million threshold
(somewhat under 1,000 ZEC at recent prices) limits these disclosures to
holders large enough to matter. It is set in US dollars so that it tracks the
real significance of a holding as the price changes.

## Why "Suspected"

Holdings of shielded ZEC are, by design, not publicly visible. A rule that
only covered confirmed holdings would be easy to evade: a Covered Party
could simply decline to ask. Requiring disclosure of suspected holders, with
the basis for the suspicion, and treating investors who decline to answer as
suspected, puts the burden of clarity on the people with the relationship
rather than on the community.

## Why signed acknowledgments, published on the Forum

An unsigned statement by a Covered Party that "our investors are aware" cannot
be checked. A signed acknowledgment from the investor, published on the Forum,
can. Quoting the ZIP text verbatim, and saying that its meaning is disputed,
means investors acknowledge the actual text and not a convenient summary.

## Why investor refusal is not itself non-compliance

A Covered Organization cannot force an existing investor to sign anything. If
a refusal counted as the organization's own non-compliance, any one investor
could disable a Key-Holder Organization or suspend a ZIP Editor. Instead, the
refusal is published with proof that the investor was told, and the
organization's people recuse from matters in which that investor has an
interest.

## Why Key-Holder Organizations keep signing disbursements

The Key-Holder Organizations' signatures are needed to pay grants that
coinholders have approved. If non-compliance removed a Key-Holder
Organization's duty to sign, a Key-Holder Organization could block approved
grants by deliberately becoming non-compliant, and grantees would be
punished for something they did not do. The consequences in this ZIP
therefore remove only the discretionary powers that a conflicted
Key-Holder Organization could misuse.

## Why ZIP Editors are suspended rather than fined or recused case by case

ZIP Editors are not paid by the ZIP Process, so there is no funding to
withhold. Case-by-case recusal depends on knowing the relationships that the
Editor has failed to disclose. Suspension is simple, objective, and fully
reversible by filing the missing disclosure; removal applies only after a
sustained failure or a finding of deliberate concealment.

## Why cover Editor Employers

Several ZIP Editors are employed by, or associated with, organizations that
raise outside capital. The relevant conflicts often arise at the employer
level (for example, an investor in the employer), not at the level of the
individual Editor. Requiring the employer to disclose, and suspending the
associated Editors if it does not, is the only lever available, since the
ZIP Process has no direct authority over those organizations.


# Open Questions

* Should Investor Acknowledgments also be mandatory (rather than recommended) for
  Coinholder Affiliates who are not immediate family members?
* Is US$1 million the right threshold for affiliations? Should it instead be
  expressed as a fraction of the coinholder-amount voting round quorum?
* Is the US$10,000 floor for donations and grants counted as Investments too
  low or too high?
* Should a Disclosed Party that has refused to acknowledge the policy for
  more than one Disclosure Quarter have its votes flagged in the published
  results of coinholder-amount voting rounds?
* Should the ZCG Committee and FPF be brought within scope by this ZIP rather
  than a future one?
* Who should act as Disclosure Reviewers for Protected Persons if the
  Key-Holder Organizations and the ZIP Editors are both conflicted? Should an
  independent reviewer (for example, outside counsel) be named instead?
* How should adoption of the changes to ZIP 1016 be evidenced: by Editor
  acceptance alone, or also by a coinholder-amount voting round?


# References

[^BCP14]: [Information on BCP 14, "RFC 2119: Key words for use in RFCs to Indicate Requirement Levels" and "RFC 8174: Ambiguity of Uppercase vs Lowercase in RFC 2119 Key Words"](https://www.rfc-editor.org/info/bcp14)

[^zip-0000-editors]: [ZIP 0: ZIP Process, ZIP Editors](zip-0000.rst#zip-editors)

[^zip-0304]: [ZIP 304: Sapling Address Signatures](zip-0304.rst)

[^zip-1015]: [ZIP 1015: Block Subsidy Allocation for Non-Direct Development Funding](zip-1015.rst)

[^zip-1015-zcg]: [ZIP 1015: Block Subsidy Allocation for Non-Direct Development Funding, Zcash Community Grants (ZCG)](zip-1015.rst#zcash-community-grants-zcg)

[^zip-1016]: [ZIP 1016: Community and Coinholder Funding Model](zip-1016.md)

[^zip-1016-disbursement]: [ZIP 1016: Community and Coinholder Funding Model, Disbursement process](zip-1016.md#disbursement-process)

[^zip-1016-admin]: [ZIP 1016: Community and Coinholder Funding Model, Administrative obligations and constraints](zip-1016.md#administrative-obligations-and-constraints)

[^draft-mcgee-keyholders]: [Draft ZIP: Update to ZIP 1016 & ZIP 271: Key-Holder Organizations](draft-mcgee-keyholders-organizations.md)

[^draft-town-square]: [Draft ZIP: The Zcash Town Square: Official Discussion and Announcement Cross-Posting](draft-emersonian-zcash-town-square.md)

[^companion-kho]: Draft ZIP on Key-Holder Organization accountability, including publication of bylaws and the ZIP 1016 legal agreement (in preparation; URL TBD).
