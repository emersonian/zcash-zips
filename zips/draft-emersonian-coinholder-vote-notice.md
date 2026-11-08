    ZIP: Unassigned
    Title: Minimum 30-Day Notice for Coinholder Votes, and a Duty on Grant Recipients to Inform Their Users
    Owners: Emerson <@emersonian>
    Status: Draft
    Category: Process
    Created: 2026-11-08
    License: MIT
    Discussions-To: <URL TBD>
    Updates: 1015, 1016


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

The terms "Zcash Funding Source", "Covered Organization", "Executive", and
"Official Account" in this document have the meanings given in the Zcash Town
Square ZIP [^draft-town-square]. If that ZIP is not Active, those definitions
are incorporated into this ZIP by reference as if set out in full here.

A **coinholder-amount voting round** is any coinholder vote held under ZIP 1016
[^zip-1016-disbursement], in which each ballot is weighted by the amount of ZEC
that the voter proves control of. This includes votes on grant applications,
separate votes on competing proposals, and additional votes on whether funding
of an existing grant should continue.

A **Coinholder Vote** is any of the following:

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

The **Poll Organizers** of a Coinholder Vote are the organizations and
individuals that announce, administer, tally, or certify it. For a
coinholder-amount voting round, the Poll Organizers are the Key-Holder
Organizations.

The **Voting Window** of a Coinholder Vote is the period during which ballots
are accepted. It **opens** at the earliest time at which any ballot is
accepted, by any method, and **closes** at the latest such time.

The **Snapshot** of a Coinholder Vote is the block height, or other point in
time, at which a voter's holdings are measured for the purpose of weighting or
eligibility.

A **Notice of Vote** is the publication described in
[Notice of Vote](#notice-of-vote).

The **Notice Date** of a Coinholder Vote is the time at which a Notice of Vote
that meets every requirement of this ZIP is first published on the Forum.

A **Funded Organization** is a Covered Organization that receives, has
received within the past 12 months, or is party to an agreement to receive,
funds from a Zcash Funding Source, whether directly or as a grantee,
sub-grantee, or Autonomous Entity. FPF, the ZCG Committee, and the Key-Holder
Organizations are Funded Organizations for the purposes of this ZIP whether or
not they also hold a grant.

An **End User** of a Funded Organization is any person who uses a product or
service that the Funded Organization develops, operates, or distributes, or
who has chosen to receive communications from it. This includes, but is not
limited to, users of its wallet applications, browser extensions, mobile and
desktop applications, block explorers, exchanges, payment processors, and
hosted services; subscribers to its newsletters and mailing lists; members of
its chat communities; and followers of its Official Accounts.

A **Wallet Application** is any software that lets a person hold, receive, or
send ZEC, including mobile, desktop, browser-extension, hardware-companion,
and command-line wallets, and any hosted or custodial service that holds ZEC
on behalf of a person.

A **Voter Notice** is a notice to End Users described in
[Duty to inform End Users](#duty-to-inform-end-users).


# Abstract

This ZIP sets a minimum notice period for every vote of Zcash coinholders. No
Coinholder Vote may open for ballots until at least 30 days after the Poll
Organizers have published, on the Zcash Community Forum, a Notice of Vote
giving the final text of every question and answer choice, the voting dates,
the Snapshot, and how to vote. A material change to any of these restarts the
30-day period.

It also requires every organization that receives funding from a Zcash Funding
Source to tell its own End Users about each upcoming Coinholder Vote, using
reasonable means. Reasonable means include, but are not limited to, a notice
displayed inside wallet applications. Voter Notices must be neutral, must not
collect or leak information about the user, and must be shown again shortly
before the Voting Window opens.

A Coinholder Vote held without the required notice is advisory only. It cannot
approve a grant from the Coinholder-Controlled Fund, and a ZIP cannot cite it
as evidence of coinholder support. A Funded Organization that does not inform
its End Users is subject to notice-and-cure, and then to suspension of its
disbursements, in the same way as under the Zcash Town Square ZIP
[^draft-town-square].


# Motivation

## Coinholders need time to take part

A coinholder who wants to vote has to do several things before the Voting
Window opens. They have to learn that a vote is happening. They have to read
the proposals, which for a change to development funding can run to many
thousands of words across several ZIPs and Forum threads. They may have to
install or update a wallet that supports voting, move ZEC into a pool or
address type that the voting method supports, and in some cases do this before
the Snapshot. Holders who keep ZEC in cold storage, on hardware wallets, or
with a custodian need longer than holders who keep ZEC in a hot wallet. If the
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

The thread also shows that basic facts a voter needs were still open shortly
before the proposal deadline. A participant asked whether voting would be
single-choice or ranked-choice, and the thread did not answer [^forum-timeline].
Another asked that "retaining the existing ZIP 1016 arrangements unchanged" be
offered as an explicit answer, separate from abstaining [^forum-timeline].
Another asked how proposals would be summarized for coinholders who had not
followed the debate [^forum-timeline]. These are reasonable questions, and a
voter cannot prepare until they are answered.

The organizers of that poll may have good reasons for moving quickly. This ZIP
does not question their good faith. It observes that nothing in any ZIP
prevented the timeline, and that the result of a vote held on that timeline
will be cited as evidence of coinholder support for changes to development
funding and a network upgrade. A poll with that much weight should not depend
on whether coinholders happened to notice a Forum post in a given week.

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
* says nothing about telling coinholders who do not read the Forum.

The coinholder vote thresholds ZIP [^draft-thresholds] requires the Key-Holder
Organizations to publish their Human Verification Methodology at least 30
days before a Voting Window opens. This ZIP generalizes that rule to the whole
Notice of Vote, and to every Coinholder Vote.

## Most coinholders never read the Forum

The Zcash Town Square ZIP [^draft-town-square] makes the Forum the official
place for Announcements, so that there is one record that anyone can check.
That is necessary, but it is not enough to reach voters. Most people who hold
ZEC learn about Zcash through the wallet they use, and many never visit the
Forum. The organizations that build those wallets, and most other widely used
Zcash software, are funded by Zcash Funding Sources: that is, by the protocol,
and so indirectly by coinholders.

It is reasonable to ask organizations funded by coinholders to tell those same
coinholders when they are being asked to vote. A short, neutral notice in a
wallet, shown a few times before a vote, costs a funded wallet team very
little and reaches far more voters than any Forum post can.


# Requirements

* Every Coinholder Vote is announced at least 30 days before its Voting
  Window opens, with all the information a voter needs to take part.
* The 30-day period cannot be worked around by announcing a vote early and
  settling its questions late.
* A Coinholder Vote held without that notice cannot bind the Key-Holder
  Organizations or be cited as evidence of coinholder support.
* Organizations funded by a Zcash Funding Source tell their End Users about
  each upcoming Coinholder Vote by reasonable means, including in-wallet
  notices where they publish a Wallet Application.
* Voter Notices are neutral, and do not collect or leak information about the
  user.
* Compliance is enforced through the grant agreements and disbursement
  schedules that the community already controls.
* The rules align with the Zcash Town Square ZIP [^draft-town-square], the
  coinholder vote thresholds ZIP [^draft-thresholds], and ZIP 1016.


# Non-requirements

* This ZIP does not change how ballots are weighted, the ZEC threshold for a
  coinholder-amount voting round, or how results are tallied.
* This ZIP does not require any organization to support voting in its
  software. A Wallet Application that does not support voting still gives a
  Voter Notice, and says where the user can vote.
* This ZIP does not require any organization to take a position on any
  question, or forbid it from doing so outside a Voter Notice.
* This ZIP does not regulate polls that are not Coinholder Votes, such as
  informal social-media polls, unless their results are cited as described in
  [Terminology](#terminology).
* This ZIP does not require a Coinholder Vote before any network upgrade, and
  does not delay the deployment of a network upgrade needed to fix a security
  vulnerability.
* This ZIP does not set notice requirements for votes of the Zcash Community
  Advisory Panel or other community panels, although it recommends them (see
  [Concurrent panel polls](#concurrent-panel-polls)).


# Privacy Implications

Voter Notices are shown inside software that people use to hold private money.
A careless implementation could tell a server, or an observer, which users
hold ZEC, how much they hold, or whether they intend to vote. The rules in
[Privacy requirements for Voter Notices](#privacy-requirements-for-voter-notices)
are intended to prevent that. In summary:

* a Wallet Application MUST NOT send any user-specific data in order to fetch,
  display, or report on a Voter Notice;
* a Voter Notice MUST be shown to all users of the application in the same
  way, and MUST NOT be targeted by balance, address type, or any other
  property of the user's wallet; and
* compliance reports under this ZIP MUST NOT include per-user data.

This ZIP adds a machine-readable Vote Notice Feed published by the Poll
Organizers. Fetching a static public file from a well-known URL reveals no
more than an ordinary update check, provided it is done without identifiers.
Wallet Applications MAY instead ship Voter Notices in an ordinary software
update, which reveals nothing new.


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

1. **Poll Organizers.** Who is organizing, administering, tallying, and
   certifying the vote, and how to contact them.
2. **Questions and answer choices.** The final text of every question that
   will appear on the ballot, and the final text and order of every answer
   choice, including any choice to keep existing arrangements unchanged, to
   abstain, or to reject all options.
3. **Voting method.** Whether each question is single-choice, approval,
   ranked-choice, or another method; how ballots are weighted; and how the
   result will be tallied, including how abstentions are treated.
4. **Dates.** The date and time, in UTC, at which the Voting Window opens and
   closes, and the expected date by which results will be published.
5. **Snapshot.** The Snapshot block height or time, and which pools, address
   types, and custody arrangements are eligible.
6. **How to vote.** Each supported method of casting a ballot, each Wallet
   Application or tool known to support it, and step-by-step instructions or a
   link to them.
7. **Effect of the result.** Whether the result is binding or advisory, under
   which ZIP, and what thresholds apply (for a coinholder-amount voting round,
   the ZEC threshold of ZIP 1016 as amended, and any human participation
   requirement under [^draft-thresholds]).
8. **Proposals.** A link to every proposal, ZIP, or grant application that the
   vote concerns, and to its Forum discussion thread.
9. **Personhood verification.** If the coinholder vote thresholds ZIP
   [^draft-thresholds] is Active, a link to the Human Verification Methodology
   that applies to the vote.
10. **Voter Notice Kit.** A link to the Voter Notice Kit described in
    [Voter Notice Kit and Vote Notice Feed](#voter-notice-kit-and-vote-notice-feed).

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

A **Material Change** is any of the following:

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
Date, or that has no Notice Date, is a **Short-Notice Vote**.

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

## Duty to inform End Users

### Who must inform

Every Funded Organization MUST give a Voter Notice to its End Users for every
Coinholder Vote, in accordance with this section, unless it has no End Users
other than its own staff.

The Poll Organizers, if they are Funded Organizations, are bound by this
section in the same way as any other Funded Organization.

### Reasonable means

A Funded Organization MUST use reasonable means to give a Voter Notice to its
End Users. Reasonable means are those that a well-run organization would use
to tell its users about something important that affects them, such as a
security update or a change of terms of service. They include, but are not
limited to:

* a notice displayed inside any Wallet Application, or other application, that
  the organization develops, operates, or distributes;
* a banner or prominent notice on the organization's website, and on the
  website or landing page of each of its products;
* a message to its email newsletters and mailing lists;
* a post on each of its Official Accounts;
* an announcement in any chat community it operates, such as a Discord server
  or Telegram group; and
* for a hosted or custodial service, a notice on the account dashboard or in
  the service's ordinary account communications.

At a minimum:

1. A Funded Organization that develops, operates, or distributes a Wallet
   Application MUST display a Voter Notice inside that Wallet Application, in
   accordance with [In-wallet notices](#in-wallet-notices).
2. Every Funded Organization MUST post a Voter Notice on each of its Official
   Accounts, and on its website if it has one.
3. Every Funded Organization that operates a newsletter or mailing list MUST
   send a Voter Notice to it, unless no issue of the newsletter or list is
   sent in the period between the Notice Date and the close of the Voting
   Window, in which case it SHOULD send one.

A Funded Organization MAY use other means that it judges more effective for
its users, in addition to these.

### Timing

A Funded Organization MUST give its first Voter Notice through each required
means no later than 7 days after the Notice Date.

It MUST give a second Voter Notice through each required means during the 7
days before the Voting Window opens, or when it opens, and SHOULD give a final
reminder during the last 3 days of the Voting Window.

If a revised Notice of Vote is published under
[Material changes](#material-changes), the Funded Organization MUST update its
Voter Notices within 7 days to reflect it.

### Content

A Voter Notice MUST contain:

* a statement that a vote of Zcash coinholders is being held;
* a one-sentence, neutral description of what the vote is about, taken from
  the Voter Notice Kit;
* the dates on which the Voting Window opens and closes, and the Snapshot if
  it is before the Voting Window;
* a link to the Notice of Vote on the Forum; and
* if the organization's own software supports voting, how to vote with it, and
  if it does not, a statement to that effect and a link to the list of
  supported methods in the Notice of Vote.

A Voter Notice SHOULD use the short or long text from the Voter Notice Kit,
translated into the languages the organization's product already supports.

### Neutrality

A Voter Notice MUST be neutral. It MUST NOT urge the user to vote for or
against any answer choice, describe any choice favourably or unfavourably, or
present the choices in an order or with emphasis other than as given in the
Notice of Vote.

Nothing in this ZIP prevents a Funded Organization, or its Executives, from
publishing their views about a Coinholder Vote elsewhere, including on their
Official Accounts and websites, provided that such views are clearly
separate from the Voter Notice and are subject to the Zcash Town Square ZIP
[^draft-town-square] where it applies. A Funded Organization MAY link from a
Voter Notice to a page listing statements by several parties, provided the
page is offered on the same terms to the authors of every proposal on the
ballot.

A Voter Notice MUST NOT be combined with a request for donations, a
promotion, or any other call to action unrelated to the vote.

## In-wallet notices

A Wallet Application published by a Funded Organization MUST display the
Voter Notice as follows:

* It MUST be shown in a place the user will see in ordinary use, such as the
  home screen, the balance screen, or a dialog shown when the application is
  opened. A notice that is only visible in a settings or "news" menu does not
  satisfy this requirement.
* It MUST be shown at least once to each user who opens the application
  during the period from 7 days after the Notice Date until the Voting Window
  opens, and again at least once to each user who opens the application during
  the Voting Window.
* It MAY be dismissable. A dismissal MUST NOT suppress the second display
  required above.
* It MUST include a link or button to the Notice of Vote, and, if the
  application supports voting, a link or button to its voting flow.
* It MUST stop being displayed when the Voting Window closes, except that it
  MAY be replaced by a neutral notice of the result.

A Wallet Application that is released on a slower cycle (for example through
app store review, or on hardware wallet firmware) MAY meet the timing
requirements by including the Voter Notice in a release published within 7
days after the Notice Date, provided that the release is published, and the
Funded Organization uses its other reasonable means in the meantime.

A Wallet Application whose interface cannot display a notice, such as a
command-line wallet or a hardware wallet screen, MUST instead print or show
the Voter Notice where it can (for example in a startup log message or in its
companion application), and its Funded Organization MUST rely on its other
reasonable means.

### Privacy requirements for Voter Notices

A Wallet Application MUST NOT, in order to fetch, display, or report on a
Voter Notice:

* send any address, viewing key, balance, transaction, note, or other
  wallet-specific data to any party;
* send any persistent identifier of the user, device, or installation;
* display the notice to some users and not others based on their balance,
  address types, pools in use, transaction history, or any other property of
  their wallet; or
* record whether a particular user saw, dismissed, or acted on the notice, in
  a way that is sent off the device.

A Wallet Application that fetches the Vote Notice Feed over the network MUST
do so in the same way as its other privacy-preserving requests, MUST NOT add
new identifiers to the request, and SHOULD use the same network privacy
protections (such as Tor) that the application uses for its other requests
where those are enabled. A Wallet Application MAY instead include the Voter
Notice in a software update.

## Voter Notice Kit and Vote Notice Feed

At the same time as the Notice of Vote, the Poll Organizers MUST publish a
**Voter Notice Kit**, linked from the Notice of Vote, containing:

* a neutral one-sentence description of the vote, of no more than 25 words;
* a neutral short notice, of no more than 60 words; and
* a neutral long notice, of no more than 250 words,

each of which meets the [Content](#content) and [Neutrality](#neutrality)
requirements of this ZIP.

The Poll Organizers MUST also publish a machine-readable **Vote Notice Feed**
at a stable URL, and SHOULD publish it in a public Git repository so that
changes are visible. The feed MUST be a static JSON document, served without
cookies or tracking, listing each Coinholder Vote whose Voting Window has not
closed, with at least the following fields:

```json
{
  "id": "2026-12-dev-fund",
  "title": "Coinholder vote on Zcash development funding",
  "summary": "<the one-sentence description>",
  "short_notice": "<the short notice>",
  "notice_url": "https://forum.zcashcommunity.com/t/...",
  "notice_date": "2026-11-09T00:00:00Z",
  "snapshot": { "height": 0, "time": "2026-11-23T00:00:00Z" },
  "voting_opens": "2026-12-09T00:00:00Z",
  "voting_closes": "2026-12-23T23:59:59Z",
  "binding": true,
  "revision": 1
}
```

The values above are examples only. The feed MAY include translations and
further fields. The `revision` field MUST be incremented on every change.

The Voter Notice Kit and the Vote Notice Feed are provided for convenience. A
Funded Organization MAY write its own Voter Notice, provided that it meets the
requirements of this ZIP.

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

## Compliance reporting

Each Funded Organization MUST include in its next regular report to the body
that administers its funding (for example, a quarterly report to ZCG, or a
report to the Key-Holder Organizations under ZIP 1016), and publish on the
Forum:

* each Coinholder Vote whose Notice Date fell in the reporting period;
* the means by which it gave Voter Notices, and the dates on which it did so;
  and
* for each Wallet Application, the version or release that displayed the
  in-wallet notice.

A Funded Organization MAY include aggregate, non-identifying figures on reach,
such as the number of newsletter recipients, but MUST NOT collect per-user
data in order to do so.

Within 14 days after each Voting Window closes, the Poll Organizers MUST
publish on the Forum a short report stating the Notice Date, any revised
Notice Dates, any postponements or corrections, and whether the vote was a
Short-Notice Vote.

## Enforcement

### Conditions of funding

From the Effective Date, FPF (for Zcash Community Grants) and the Key-Holder
Organizations (for the Coinholder-Controlled Fund) MUST include compliance
with this ZIP as a condition in every grant agreement entered into, renewed,
or amended with a Funded Organization. Grant agreements in force at the
Effective Date SHOULD be amended to include it at the earliest opportunity,
and MUST include it on renewal.

FPF, the ZCG Committee, and the Key-Holder Organizations are themselves bound
by this ZIP, and compliance with it forms part of their Transparency and
Accountability obligations under ZIP 1015 [^zip-1015-transparency] and ZIP
1016.

### Reporting of non-compliance

Any person MAY report an apparent failure to comply with this ZIP by posting in
the category designated under
[Forum category and register of votes](#forum-category-and-register-of-votes).
A report SHOULD include a screenshot, an archived copy, or a description of
what was or was not shown, and the version of any Wallet Application
concerned.

### Notice and cure

When a report is made, or when FPF, the ZCG Committee, or a Key-Holder
Organization otherwise becomes aware of an apparent failure by a Funded
Organization to give a Voter Notice, the body that administers the relevant
Zcash Funding Source MUST give the Funded Organization notice on the Forum
within 3 days.

The Funded Organization then has 5 days from the notice (the "cure period") to
give the missing Voter Notice, or to correct it, or to explain on the Forum
why it is not required to. Because the purpose of a Voter Notice is to reach
users before they vote, the cure period ends no later than the time at which
the Voting Window opens, unless the notice is given less than 5 days before
then, in which case the cure period ends 2 days after the notice.

A failure that is cured within the cure period is a "cured failure". It is
recorded in the register, but has no further consequence except as set out
below.

### Substantial violation

A Funded Organization commits a "substantial violation" of this ZIP if:

* it does not cure a failure within the cure period;
* it gives a Voter Notice that breaches the [Neutrality](#neutrality)
  requirement, or the
  [Privacy requirements for Voter Notices](#privacy-requirements-for-voter-notices),
  and does not withdraw or correct it within the cure period; or
* it has cured failures in respect of two or more Coinholder Votes within any
  period of 12 months.

When a grantee commits a substantial violation:

* FPF and the Key-Holder Organizations, as applicable, MUST suspend any
  scheduled disbursement to it from the Zcash Funding Source they administer
  until the violation is cured, and in the case of repeated failures, until it
  has complied in full for the next Coinholder Vote;
* for a grant from the Coinholder-Controlled Fund, the Key-Holder
  Organizations SHOULD treat the violation as a contentious issue for which a
  further coinholder-amount voting round is held on whether funding should
  continue, as provided in ZIP 1016 [^zip-1016-disbursement]; and
* the ZCG Committee, and coinholders in any coinholder-amount voting round,
  SHOULD take the violation into account in any future funding decision for
  that Funded Organization.

A privacy breach under this ZIP is also a security issue for the users
affected. A Funded Organization that commits one MUST, in addition, publish a
description of what data was exposed and to whom, in the same way it would
for any other privacy vulnerability in its software.

When FPF, the ZCG Committee, or a Key-Holder Organization commits a
substantial violation, or acts as a Poll Organizer of a Short-Notice Vote that
it then treats as binding, it constitutes a failure to meet its Transparency
and Accountability obligations under ZIP 1015 and ZIP 1016, and is subject to
the enforcement provisions of those ZIPs [^zip-1015-enforcement].

All notices, explanations, cures, suspensions, and resumptions of disbursement
under this section MUST be published on the Forum.

### Disputes

If a Funded Organization disputes that it is required to give a Voter Notice,
or that its means were reasonable, the body that administers the relevant
Zcash Funding Source MUST decide the question and publish its decision and
reasons on the Forum. Where a Key-Holder Organization or FPF is itself the
Funded Organization concerned, it MUST NOT take part in that decision; the
decision is instead made by the remaining Key-Holder Organizations, or, for
FPF, by the ZCG Committee.

<details>
<summary>

### Rationale for enforcement through funding

</summary>

As with the Zcash Town Square ZIP [^draft-town-square], a Process ZIP can only
compel action through the obligations and processes that the community
already controls. For the notice period, the most effective sanction is the
one that falls on the result: a Short-Notice Vote simply does not count. That
needs no new institution, and it removes any incentive to rush a vote.

For the duty to inform End Users, the lever is the grant agreement and the
disbursement schedule. The notice-and-cure step keeps the consequence
proportionate. A wallet team that misses a release and fixes it promptly loses
nothing. Only an organization that refuses to inform its users, or uses a
Voter Notice to campaign or to collect data, has its disbursements suspended,
and only until it complies.
</details>

## Activation

This ZIP becomes effective when its Status becomes Active (the "Effective
Date").

The [Minimum notice period](#minimum-notice-period) and the
[Effect of insufficient notice](#effect-of-insufficient-notice) apply to every
Coinholder Vote whose Voting Window opens on or after the Effective Date.

The [Duty to inform End Users](#duty-to-inform-end-users) applies to every
Coinholder Vote whose Notice Date is on or after the Effective Date. For a
Funded Organization whose grant agreement does not yet include the condition
in [Conditions of funding](#conditions-of-funding), the duty applies as a
SHOULD until its agreement is amended or renewed.

Poll Organizers and Funded Organizations are encouraged to comply voluntarily
from the time this ZIP is published as a Draft.


# Rationale

## Why 30 days

Thirty days matches the community review period that ZIP 1016 already
requires for grant applications [^zip-1016-disbursement], and the publication
period for the Human Verification Methodology in the coinholder vote
thresholds ZIP [^draft-thresholds]. Using the same figure everywhere means
that a single Notice of Vote, published 30 days ahead, can satisfy all three.

It is long enough for a mobile wallet team to ship an app store release with a
Voter Notice, for a holder in cold storage or with a custodian to make
arrangements, and for proposal authors and critics to respond to one another
on the Forum. It is short enough that the community can still act quickly when
it needs to: four or five Coinholder Votes a year remain possible on any
single question.

## Why the Snapshot must be at least 14 days after notice

Voting methods may only support some pools or address types, or require ZEC
to be in a wallet that supports voting at the Snapshot. A holder who first
learns about a vote after the Snapshot has already lost the chance to take
part, however long the Voting Window is. Fourteen days leaves time to move
funds after the first Voter Notice, which this ZIP requires within 7 days.

## Why a Short-Notice Vote is advisory rather than forbidden

Forbidding a vote is hard to enforce and may be unwise, because sometimes the
community needs a quick reading of opinion. Making the result advisory keeps
that option open while ensuring that a rushed vote cannot bind the Key-Holder
Organizations or be presented in a ZIP as the considered view of coinholders.
This matches the approach of the coinholder vote thresholds ZIP
[^draft-thresholds], under which a vote that does not meet its requirements is
also advisory.

## Why place the duty on funded organizations

Organizations that receive money from a Zcash Funding Source are funded by the
protocol, and so by coinholders. Asking them to tell coinholders about votes
is a small and fair condition of that funding. It is also where the users
are: the main Zcash wallets are built by funded teams.

Unfunded organizations, such as exchanges and independent wallets, are not
bound, because a Process ZIP has no lever over them. The Voter Notice Kit and
Vote Notice Feed are designed so that they can display notices easily if they
choose to, and Poll Organizers SHOULD invite them to.

## Why in-wallet notices

A Forum post reaches the people who already follow governance. An in-wallet
notice reaches the people who hold ZEC. A notice shown twice per vote, and
only a few times a year, is a small burden on the user, comparable to an
update prompt.

## Why neutrality

A wallet's notice reaches its whole user base and carries the authority of the
software the user trusts with their money. If a funded wallet could use that
position to campaign for one answer, the duty to inform would become a tool
for whichever organizations ship the most popular wallets, and several of
those organizations are frequently parties to the questions being voted on.
Organizations remain free to campaign in their own voice, elsewhere. A Forum
participant made a related argument in the motivating thread, comparing
proposal authors framing their own ballot question with ballot design in
public elections [^forum-timeline].

## Why the Vote Notice Feed is static and optional

A static, public JSON file can be fetched without revealing anything more than
any other update check, and can be mirrored or bundled into releases. Making
it optional lets each wallet team choose the approach that fits its own
privacy model, including shipping the notice in a release and never fetching
anything.

## Alternatives considered

* **Counting 30 days from the first announcement.** Rejected, because it lets
  the questions be settled late. See
  [Rationale for restarting the clock](#rationale-for-restarting-the-clock).
* **A longer notice period, such as 60 days.** Possible, but it would slow
  every vote, including routine quarterly grant rounds, and the 30-day figure
  aligns with existing rules. See [Open questions](#open-questions).
* **An emergency exception allowing shorter notice.** Not included. No ZIP
  requires a Coinholder Vote before a security fix can be deployed, so there
  is no emergency that a shorter-notice binding vote is needed for. A
  Short-Notice Vote remains available as an advisory measure.
* **Requiring all Zcash wallets to display notices.** Not possible through a
  Process ZIP. See
  [Why place the duty on funded organizations](#why-place-the-duty-on-funded-organizations).


# Open questions

* Should the minimum notice period be longer than 30 days for votes on
  protocol changes or development funding, as opposed to routine grant
  rounds?
* Is 14 days the right minimum gap between the Notice Date and the Snapshot?
* Should this ZIP apply, as a SHOULD, to the coinholder and community panel
  polls currently scheduled to open on 16 November 2026, asking their
  organizers to postpone the Voting Window so that it gives 30 days' notice?
* Should the notice requirements also bind polls of the Zcash Community
  Advisory Panel and other community panels, rather than only recommending
  them?
* Should Funded Organizations that hold only small grants, or individual
  grantees with no products, be exempt from the duty to inform End Users?
* Should exchanges and custodians that are not Funded Organizations be invited
  to sign a voluntary commitment to display Voter Notices, and should the
  register record which have done so?
* Should the Poll Organizers be required, rather than recommended, to publish
  neutral summaries of each proposal, and should someone independent of the
  proposal authors and the Poll Organizers prepare them?


# References

[^BCP14]: [Information on BCP 14 — "RFC 2119: Key words for use in RFCs to Indicate Requirement Levels" and "RFC 8174: Ambiguity of Uppercase vs Lowercase in RFC 2119 Key Words"](https://www.rfc-editor.org/info/bcp14)

[^zip-1015]: [ZIP 1015: Block Subsidy Allocation for Non-Direct Development Funding](zip-1015.rst)

[^zip-1015-transparency]: [ZIP 1015: Block Subsidy Allocation for Non-Direct Development Funding — Transparency and Accountability](zip-1015.rst#transparency-and-accountability)

[^zip-1015-enforcement]: [ZIP 1015: Block Subsidy Allocation for Non-Direct Development Funding — Enforcement](zip-1015.rst#enforcement)

[^zip-1016]: [ZIP 1016: Community and Coinholder Funding Model](zip-1016.md)

[^zip-1016-disbursement]: [ZIP 1016: Community and Coinholder Funding Model — Disbursement process](zip-1016.md#disbursement-process)

[^draft-mcgee-keyholders]: [Draft ZIP: Update to ZIP 1016 & ZIP 271: Key-Holder Organizations](draft-mcgee-keyholders-organizations.md)

[^draft-town-square]: [Draft ZIP: The Zcash Town Square: Official Discussion and Announcement Cross-Posting](draft-emersonian-zcash-town-square.md)

[^draft-thresholds]: [Draft ZIP: Update to ZIP 1016: Higher ZEC Threshold, Minimum Human Participation, and Published Proof-of-Personhood for Coinholder Votes](draft-emersonian-coinholder-vote-thresholds.md)

[^forum-timeline]: [Zcash Community Forum: "ZCG and the Dev Fund Timeline for Proposals and Polling", first post 2026-11-05, and replies to 2026-11-08](https://forum.zcashcommunity.com/t/zcg-and-the-dev-fund-timeline-for-proposals-and-polling/58906)
