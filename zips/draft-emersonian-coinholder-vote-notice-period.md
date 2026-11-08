    ZIP: Unassigned
    Title: Update to ZIP 1016: Minimum 30-Day Notice for Coinholder Votes
    Owners: Emerson <@emersonian>
    Status: Draft
    Category: Process
    Created: 2026-11-08
    License: MIT
    Discussions-To: <URL TBD>
    Updates: 1016


# Terminology

The key words "MUST", "MUST NOT", "SHALL", "SHOULD", "SHOULD NOT", and "MAY" in
this document are to be interpreted as described in BCP 14 [^BCP14] when, and
only when, they appear in all capitals.

The terms "Zcash Community Grants" (or "ZCG"), "ZCG Committee", and "Financial
Privacy Foundation" (or "FPF") in this document are to be interpreted as
defined in ZIP 1015 [^zip-1015].

The terms "Coinholder-Controlled Fund" and "Key-Holder Organizations" in this
document are to be interpreted as described in ZIP 1016 [^zip-1016], as amended
by any ZIP that updates the membership of the Key-Holder Organizations (see for
example [^draft-mcgee-keyholders]).

"ZEC" refers to the native currency of Zcash on Mainnet.

"Zcash Community Forum" (or "the Forum") means the discussion forum hosted at
<https://forum.zcashcommunity.com/>, or any successor designated as the Zcash
Town Square under [^draft-town-square].

The terms "Covered Organization" and "Other Platform" in this document have
the meanings given in the Zcash Town Square ZIP [^draft-town-square]. If that
ZIP is not Active, those definitions are incorporated into this ZIP by
reference as if set out in full here.

The terms below are to be interpreted as follows:

Coinholder-amount voting round

: Any coinholder vote held under ZIP 1016 [^zip-1016-disbursement], in which
  each ballot is weighted by the amount of ZEC that the voter proves control of.
  This includes votes on grant applications, separate votes on competing
  proposals, and additional votes on whether funding of an existing grant should
  continue.

Coinholder Vote

: Any of the following:

  * a coinholder-amount voting round;
  * any other poll, vote, or signalling exercise in which holders of ZEC are
    asked to express a preference by proving control of ZEC, that is organized,
    administered, or certified by one or more Key-Holder Organizations, by FPF or
    the ZCG Committee, or by any Covered Organization; and
  * any poll of ZEC holders, by whoever it is organized, whose result is cited in
    a ZIP, or in a proposal to change a ZIP or to deploy a network upgrade, as
    evidence of coinholder support or opposition.

  This definition deliberately includes polls on protocol changes, network
  upgrades, and the structure of development funding, as well as grant votes. It
  matches the definition of "coinholder poll" in the coinholder vote thresholds
  ZIP [^draft-thresholds].

Poll Organizers

: The Poll Organizers of a Coinholder Vote are the organizations and individuals
  that announce, administer, tally, or certify it. For a coinholder-amount
  voting round, the Poll Organizers are the Key-Holder Organizations.

Voting Window

: The Voting Window of a Coinholder Vote is the period during which ballots are
  accepted. It opens at the earliest time at which any ballot is accepted, by
  any method, and closes at the latest such time.

Snapshot

: The Snapshot of a Coinholder Vote is the block height, or other point in time,
  at which a voter's holdings are measured for the purpose of weighting or
  eligibility.

Notice of Vote

: The publication described in [Notice of Vote](#notice-of-vote).

Notice Date

: The Notice Date of a Coinholder Vote is the time at which a Notice of Vote
  that meets every requirement of this ZIP is first published on the Forum.


# Abstract

This ZIP sets a minimum notice period for every vote of Zcash coinholders. No
Coinholder Vote may open for ballots until at least 30 days after the Poll
Organizers have published, on the Zcash Community Forum, a Notice of Vote
giving the final text of every question and answer choice, the voting dates,
the Snapshot, and how to vote. A material change to any of these restarts the
30-day period, and the Snapshot cannot be taken until at least 14 days after
the notice.

A Coinholder Vote held without the required notice is advisory only. It cannot
approve a grant from the Coinholder-Controlled Fund, and a ZIP cannot cite it
as evidence of coinholder support. Anyone may still hold a quick poll, but its
result does not carry the weight of a properly noticed vote.

The ZIP has no significant privacy implications. A companion draft
[^draft-voter-notices] would require organizations funded by the community to
tell their own users about each vote, including through in-wallet notices.
The two can be adopted separately or together.


# Motivation

## Coinholders need time to take part

Before the Voting Window opens, a coinholder has to learn that a vote is
happening, read the proposals (which for development funding can run to many
thousands of words), perhaps install or update a wallet that supports voting,
and perhaps move ZEC into a supported pool before the Snapshot. Holders using
cold storage, hardware wallets, or custodians need longer. If the
coinholder vote thresholds ZIP [^draft-thresholds] is adopted, a coinholder
who wants to be counted as a verified coinholder-person will also have to
complete personhood verification.

A vote that opens a few days after it is announced reaches only the holders
who happen to read the Forum that week. That favours insiders, Poll
Organizers, and large holders with staff who follow governance full time, and
it disadvantages ordinary holders, who are the people a coinholder vote is
supposed to hear from.

## The November 2026 dev fund poll

The current timeline for polling on the future of Zcash development funding
is an example of how little notice a Coinholder Vote can receive under the
current rules.

On 2026-11-05 at 15:45 UTC, a Forum post on behalf of "Project Tachyon,
Shielded Labs, Valar Group, the Zcash Foundation, and ZODL (the five
organizations responsible for coordinating the coinholder voting chain)" set
out the following timeline [^forum-timeline]:

| Date (2026, UTC) | Step |
|---|---|
| Thursday 5 November | Timeline announced on the Forum. |
| Sunday 8 November, 23:59 | Deadline for proposals and ZIPs. |
| Monday 9 November | Proposed poll questions and possible answers published for feedback. |
| 9 to 15 November | Community discussion; changes to the questions and answer choices may be suggested "before polling begins". |
| Monday 16 November | "Polls for coinholders and community panels open". |
| Monday 30 November, 23:59 | Polls close. |

The post describes this as "an expedited timeline because tensions were high"
[^forum-timeline].

Under that timeline:

* the vote was first announced about 10 days and 8 hours before it opened;
* the proposed questions and answer choices are published 7 days before it
  opens, and the final text may change at any point up to the opening; and
* anyone who wanted to submit a proposal for the poll had about 3 days and 8
  hours to do so.

Basic facts were still open shortly before the proposal deadline. Participants
asked whether voting would be single-choice or ranked-choice, whether keeping
the existing ZIP 1016 arrangements would be an explicit option, and how
proposals would be summarized, and the thread did not answer
[^forum-timeline]. A voter cannot prepare until such questions are settled.

The organizers may have good reasons for moving quickly, and this ZIP does not
question their good faith. But nothing in any ZIP prevented the timeline, and
the result will be cited as evidence of coinholder support for changes to
development funding and a network upgrade. A poll with that much weight
should not depend on whether coinholders noticed a Forum post in a given week.

Under this ZIP, if the final questions and answer choices had been published
on 9 November, the earliest that the poll could have opened is 9 December
2026. If the final text were only settled at the end of the discussion period
on 15 November, the earliest opening would be 15 December 2026.

## Existing rules are narrower

ZIP 1016 says that "grant applications must be submitted for community review
30 days prior to coinholder voting" [^zip-1016-disbursement]. That rule:

* applies only to grant applications under the Coinholder-Controlled Fund, not
  to polls on protocol changes or development funding;
* starts the clock on the submission of an application, not on the
  announcement of the vote, its dates, its questions, or how to vote; and
* does not say what a voter needs to be told, or where.

The coinholder vote thresholds ZIP [^draft-thresholds] requires the Key-Holder
Organizations to publish their Human Verification Methodology at least 30
days before a Voting Window opens. This ZIP generalizes that rule to the whole
Notice of Vote, and to every Coinholder Vote.


# Privacy Implications

This ZIP has no significant privacy implications. It governs when and where a
vote is announced, and what the announcement says. It does not change how
ballots are cast or counted, and it does not require any information about
voters to be collected or published.


# Requirements

* Every Coinholder Vote is announced at least 30 days before its Voting
  Window opens, with all the information a voter needs to take part.
* The 30-day period cannot be worked around by announcing a vote early and
  settling its questions late.
* A Coinholder Vote held without that notice cannot bind the Key-Holder
  Organizations or be cited as evidence of coinholder support.
* Anyone can see, in one place, which votes are coming up and whether each
  one was properly noticed.
* The rules align with the Zcash Town Square ZIP [^draft-town-square], the
  coinholder vote thresholds ZIP [^draft-thresholds], and ZIP 1016.


# Non-requirements

* This ZIP does not change how ballots are weighted, the ZEC threshold for a
  coinholder-amount voting round, or how results are tallied.
* This ZIP does not require any organization to tell its users about a vote.
  That is the subject of the companion draft [^draft-voter-notices].
* This ZIP does not regulate polls that are not Coinholder Votes, such as
  informal social-media polls, unless their results are cited as described in
  [Terminology](#terminology).
* This ZIP does not require a Coinholder Vote before any network upgrade, and
  does not delay the deployment of a network upgrade needed to fix a security
  vulnerability.
* This ZIP does not set notice requirements for votes of the Zcash Community
  Advisory Panel or other community panels, although it recommends them (see
  [Concurrent panel polls](#concurrent-panel-polls)).


# Specification

## Minimum notice period

A Coinholder Vote's Voting Window MUST NOT open earlier than 30 days (720
hours) after its Notice Date.

The Snapshot of a Coinholder Vote MUST NOT be earlier than 14 days (336 hours)
after its Notice Date, unless the Snapshot is taken at the time each ballot is
cast. This gives holders time to move ZEC into a wallet, pool, or address type
that the voting method supports.

The Voting Window of a Coinholder Vote SHOULD remain open for at least 14
days.

For a coinholder-amount voting round, the 30-day period in this section runs
in addition to, and may run at the same time as, the 30-day community review
period for grant applications in ZIP 1016 [^zip-1016-disbursement]. Both MUST
be satisfied.

## Notice of Vote

The Poll Organizers of a Coinholder Vote MUST publish a Notice of Vote on the
Forum, as a new topic in the category designated under
[Forum category and register of votes](#forum-category-and-register-of-votes).
A Notice of Vote published only on an Other Platform (as defined in the Zcash
Town Square ZIP [^draft-town-square]) does not satisfy this ZIP.

A Notice of Vote MUST state, in plain language:

1. Poll Organizers: who is organizing, administering, tallying, and
   certifying the vote, and how to contact them.
2. Questions and answer choices: the final text of every question that
   will appear on the ballot, and the final text and order of every answer
   choice, including any choice to keep existing arrangements unchanged, to
   abstain, or to reject all options.
3. Voting method: whether each question is single-choice, approval,
   ranked-choice, or another method; how ballots are weighted; and how the
   result will be tallied, including how abstentions are treated.
4. Dates: the date and time, in UTC, at which the Voting Window opens and
   closes, and the expected date by which results will be published.
5. Snapshot: the Snapshot block height or time, and which pools, address
   types, and custody arrangements are eligible.
6. How to vote: each supported method of casting a ballot, each Wallet
   Application or tool known to support it, and step-by-step instructions or a
   link to them.
7. Effect of the result: whether the result is binding or advisory, under
   which ZIP, and what thresholds apply (for a coinholder-amount voting round,
   the ZEC threshold of ZIP 1016 as amended, and any human participation
   requirement under [^draft-thresholds]).
8. Proposals: a link to every proposal, ZIP, or grant application that the
   vote concerns, and to its Forum discussion thread.
9. Personhood verification: if the coinholder vote thresholds ZIP
   [^draft-thresholds] is Active, a link to the Human Verification Methodology
   that applies to the vote.
10. Voter notices: if the companion voter notice ZIP [^draft-voter-notices]
    is Active, a link to the Voter Notice Kit that it requires.

The Notice of Vote SHOULD include a neutral summary of each proposal, of no
more than 300 words each, prepared by the Poll Organizers and offered to each
proposal's authors for comment before publication. A proposal's author MAY
publish a statement of up to 300 words in reply in the same topic, and the
Poll Organizers MUST link to it from the Notice of Vote.

The Poll Organizers of a Coinholder Vote that is held at the same time as, or
on the same questions as, another Coinholder Vote MAY publish one Notice of
Vote for both, provided that it meets the requirements of this section for
each.

## Material changes

After the Notice Date, the Poll Organizers MUST NOT make a Material Change to
the Coinholder Vote unless they publish a revised Notice of Vote. The revised
Notice of Vote becomes the new Notice Date for the purposes of the
[Minimum notice period](#minimum-notice-period).

A "Material Change" is any of the following:

* adding a question, or removing one;
* changing the text of a question or of an answer choice in a way that could
  change how a reasonable voter would vote;
* adding, removing, or reordering answer choices;
* changing the voting method, the weighting of ballots, or the tally rules;
* moving the opening of the Voting Window earlier, or moving its close earlier;
* moving the Snapshot, or changing which pools, address types, or custody
  arrangements are eligible; or
* changing whether the result is binding or advisory.

The following are not Material Changes, but MUST be published as a reply in
the Notice of Vote topic, with an explanation, as soon as they are made:

* correcting a typographical error that does not change meaning;
* adding a supported Wallet Application or voting tool;
* moving the opening of the Voting Window later, or moving its close later;
  and
* postponing the whole vote.

A Coinholder Vote that is postponed MAY keep its original Notice Date, provided
that no Material Change is made. If a postponement is caused by a security
vulnerability in the voting method, the Poll Organizers MAY also correct the
vulnerability without restarting the notice period, provided that the
correction does not change any item listed in
[Notice of Vote](#notice-of-vote) other than dates, and that the change and the
reason for it are published immediately.

<details>
<summary>

### Rationale for restarting the clock

</summary>

A rule that counted 30 days from the first announcement would let Poll
Organizers announce "a vote on development funding" a month ahead, and then
publish the actual questions a few days before the Voting Window opens. That
would comply in form and defeat the purpose. Voters prepare to vote on a
specific ballot. The clock runs from the time the ballot is known.

Moving dates later, extending the Voting Window, and adding tools only give
voters more opportunity to take part, so they do not restart the clock.
</details>

## Effect of insufficient notice

A Coinholder Vote whose Voting Window opens less than 30 days after its Notice
Date, or that has no Notice Date, is a "Short-Notice Vote".

A Short-Notice Vote is advisory only. In particular:

* a coinholder-amount voting round that is a Short-Notice Vote MUST NOT be
  treated as approving a grant, approving the continuation of a grant, or
  selecting between competing proposals under ZIP 1016, and the Key-Holder
  Organizations MUST NOT sign any disbursement from the Coinholder-Controlled
  Fund on the strength of it;
* a ZIP MUST NOT cite the result of a Short-Notice Vote as evidence of
  coinholder support or opposition, and any ZIP, or proposal to deploy a
  network upgrade, that refers to it MUST state that it was a Short-Notice
  Vote; and
* the Poll Organizers MUST label the result "Advisory: Short-Notice Vote" in
  every publication of it, on the Forum and on any Other Platform.

This section does not prevent anyone from holding a Short-Notice Vote, or from
discussing its result. It only prevents the result from carrying the weight of
a properly noticed vote.

The Poll Organizers of a Coinholder Vote that is scheduled when this ZIP
becomes Active, and that would be a Short-Notice Vote, SHOULD postpone its
Voting Window so that it complies. See [Activation](#activation).

## Forum category and register of votes

The Poll Organizers of coinholder-amount voting rounds (that is, the
Key-Holder Organizations) MUST request that the operator of the Forum provide
a category for Notices of Vote, and MUST maintain in it a pinned register
listing every Coinholder Vote that they are aware of, its Notice Date, its
Voting Window, and whether it is, or would be, a Short-Notice Vote.

If the Zcash Town Square ZIP [^draft-town-square] is Active, the category
SHOULD be within the categories designated under that ZIP, and a Notice of
Vote that is published there is also an Announcement for the purposes of that
ZIP.

## Concurrent panel polls

When a poll of the Zcash Community Advisory Panel, or of any other community
panel, is held at the same time as a Coinholder Vote or on the same questions,
its organizers SHOULD give the same notice and include the panel poll in the
same Notice of Vote. This ZIP does not make a panel poll advisory if they do
not.

## Reporting

Within 14 days after each Voting Window closes, the Poll Organizers MUST
publish on the Forum a short report stating the Notice Date, any revised
Notice Dates, any postponements or corrections, and whether the vote was a
Short-Notice Vote.

## Enforcement

The main consequence of insufficient notice falls on the result: a
Short-Notice Vote is advisory, as set out in
[Effect of insufficient notice](#effect-of-insufficient-notice).

In addition, when FPF, the ZCG Committee, or a Key-Holder Organization acts as
a Poll Organizer of a Short-Notice Vote and then treats it as binding, or fails
to publish a report required by this ZIP, it fails to meet its Transparency
and Accountability obligations under ZIP 1015 [^zip-1015-transparency] and ZIP
1016, and is subject to the enforcement provisions of those ZIPs
[^zip-1015-enforcement].

## Activation

This ZIP becomes effective when its Status becomes Active (the "Effective
Date"). It applies to every Coinholder Vote whose Voting Window opens on or
after the Effective Date.

Poll Organizers are encouraged to comply voluntarily from the time this ZIP is
published as a Draft.


# Rationale

## Why 30 days

Thirty days matches the community review period that ZIP 1016 already
requires for grant applications [^zip-1016-disbursement], and the publication
period for the Human Verification Methodology in the coinholder vote
thresholds ZIP [^draft-thresholds]. Using the same figure everywhere means
that a single Notice of Vote, published 30 days ahead, can satisfy all three.

It is long enough for wallet teams to ship any changes a vote needs, for a
holder in cold storage or with a custodian to make
arrangements, and for proposal authors and critics to respond to one another
on the Forum. It is short enough that the community can still act quickly when
it needs to: four or five Coinholder Votes a year remain possible on any
single question.

## Why the Snapshot must be at least 14 days after notice

Voting methods may only support some pools or address types, or require ZEC
to be in a wallet that supports voting at the Snapshot. A holder who first
learns about a vote after the Snapshot has already lost the chance to take
part, however long the Voting Window is. Fourteen days leaves time for news of
the vote to spread and for holders to move funds before the Snapshot.

## Why a Short-Notice Vote is advisory rather than forbidden

Forbidding a vote is hard to enforce and may be unwise, because sometimes the
community needs a quick reading of opinion. Making the result advisory keeps
that option open while ensuring that a rushed vote cannot bind the Key-Holder
Organizations or be presented in a ZIP as the considered view of coinholders.
This matches the approach of the coinholder vote thresholds ZIP
[^draft-thresholds], under which a vote that does not meet its requirements is
also advisory.

## Alternatives considered

* Counting 30 days from the first announcement: rejected, because it lets
  the questions be settled late. See
  [Rationale for restarting the clock](#rationale-for-restarting-the-clock).
* A longer notice period, such as 60 days: possible, but it would slow
  every vote, including routine quarterly grant rounds, and the 30-day figure
  aligns with existing rules. See [Open questions](#open-questions).
* An emergency exception allowing shorter notice: not included. No ZIP
  requires a Coinholder Vote before a security fix can be deployed, so there
  is no emergency that a shorter-notice binding vote is needed for. A
  Short-Notice Vote remains available as an advisory measure.


# Open questions

* Should the minimum notice period be longer than 30 days for votes on
  protocol changes or development funding, as opposed to routine grant
  rounds?
* Is 14 days the right minimum gap between the Notice Date and the Snapshot?
* Should this ZIP apply, as a recommendation, to the coinholder and community
  panel polls currently scheduled to open on 16 November 2026, asking their
  organizers to postpone the Voting Window so that it gives 30 days' notice?
* Should the notice requirements also bind polls of the Zcash Community
  Advisory Panel and other community panels, rather than only recommending
  them?
* Should the Poll Organizers be required, rather than recommended, to publish
  neutral summaries of each proposal, and should someone independent of the
  proposal authors and the Poll Organizers prepare them?
* Should this ZIP stay separate from the companion voter notice draft
  [^draft-voter-notices], or be merged with it after community polling?


# References

[^BCP14]: [Information on BCP 14, "RFC 2119: Key words for use in RFCs to Indicate Requirement Levels" and "RFC 8174: Ambiguity of Uppercase vs Lowercase in RFC 2119 Key Words"](https://www.rfc-editor.org/info/bcp14)

[^zip-1015]: [ZIP 1015: Block Subsidy Allocation for Non-Direct Development Funding](zip-1015.rst)

[^zip-1015-transparency]: [ZIP 1015: Block Subsidy Allocation for Non-Direct Development Funding, Transparency and Accountability](zip-1015.rst#transparency-and-accountability)

[^zip-1015-enforcement]: [ZIP 1015: Block Subsidy Allocation for Non-Direct Development Funding, Enforcement](zip-1015.rst#enforcement)

[^zip-1016]: [ZIP 1016: Community and Coinholder Funding Model](zip-1016.md)

[^zip-1016-disbursement]: [ZIP 1016: Community and Coinholder Funding Model, Disbursement process](zip-1016.md#disbursement-process)

[^draft-mcgee-keyholders]: [Draft ZIP: Update to ZIP 1016 & ZIP 271: Key-Holder Organizations](draft-mcgee-keyholders-organizations.md)

[^draft-town-square]: [Draft ZIP: The Zcash Town Square: Official Discussion and Announcement Cross-Posting](draft-emersonian-zcash-town-square.md)

[^draft-thresholds]: [Draft ZIP: Update to ZIP 1016: Higher ZEC Threshold, Minimum Human Participation, and Published Proof-of-Personhood for Coinholder Votes](draft-emersonian-coinholder-vote-thresholds.md)

[^forum-timeline]: [Zcash Community Forum: "ZCG and the Dev Fund Timeline for Proposals and Polling", first post 2026-11-05, and replies to 2026-11-08](https://forum.zcashcommunity.com/t/zcg-and-the-dev-fund-timeline-for-proposals-and-polling/58906)

[^draft-voter-notices]: [Draft ZIP: Duty on Funded Organizations to Inform Their Users of Coinholder Votes](draft-emersonian-coinholder-vote-user-notices.md)
