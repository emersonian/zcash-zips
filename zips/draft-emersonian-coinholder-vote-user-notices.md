    ZIP: Unassigned
    Title: Duty on Funded Organizations to Inform Their Users of Coinholder Votes
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

The terms "Coinholder Vote", "Coinholder-amount voting round", "Poll
Organizers", "Voting Window", "Snapshot", "Notice of Vote", "Notice Date", and
"Material Change" in this document have the meanings given in the coinholder
vote notice ZIP [^draft-notice-period].

The terms below are to be interpreted as follows:

Funded Organization

: A Covered Organization that receives, has received within the past 12 months,
  or is party to an agreement to receive, funds from a Zcash Funding Source,
  whether directly or as a grantee, sub-grantee, or Autonomous Entity. FPF, the
  ZCG Committee, and the Key-Holder Organizations are Funded Organizations for
  the purposes of this ZIP whether or not they also hold a grant.

End User

: An End User of a Funded Organization is any person who uses a product or
  service that the Funded Organization develops, operates, or distributes, or
  who has chosen to receive communications from it. This includes, but is not
  limited to, users of its wallet applications, browser extensions, mobile and
  desktop applications, block explorers, exchanges, payment processors, and
  hosted services; subscribers to its newsletters and mailing lists; members of
  its chat communities; and followers of its Official Accounts.

Wallet Application

: Any software that lets a person hold, receive, or send ZEC, including mobile,
  desktop, browser-extension, hardware-companion, and command-line wallets, and
  any hosted or custodial service that holds ZEC on behalf of a person.

Voter Notice

: A notice to End Users described in [Duty to inform End
  Users](#duty-to-inform-end-users).


# Abstract

This ZIP requires every organization that receives funding from a Zcash
Funding Source to tell its own End Users about each upcoming Coinholder Vote,
using reasonable means. Reasonable means include, but are not limited to, a
notice displayed inside wallet applications, posts on the organization's
official accounts and website, and messages to its mailing lists. A first
notice is due within 7 days after the vote is announced, and a second in the
week before voting opens.

Voter Notices must be neutral. They must not collect or leak information about
the user, must not be targeted by balance or address type, and must not be
combined with any other call to action. The Poll Organizers publish a neutral
Voter Notice Kit and a static Vote Notice Feed that wallets can use.

A Funded Organization that does not inform its End Users is subject to
notice-and-cure, and then to suspension of its disbursements, in the same way
as under the Zcash Town Square ZIP [^draft-town-square]. This ZIP builds on
the companion notice-period ZIP [^draft-notice-period], which sets when and
how a vote is announced.


# Motivation

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

The companion notice-period ZIP [^draft-notice-period] makes sure that every
Coinholder Vote is announced on the Forum at least 30 days ahead. That gives
voters time to prepare, but only if they hear about the vote. This ZIP closes
that gap by asking the organizations that already reach coinholders, through
their wallets and other products, to pass the notice on.


# Privacy Implications

Voter Notices are shown inside software that people use to hold private money.
A careless implementation could tell a server, or an observer, which users
hold ZEC, how much they hold, or whether they intend to vote. The rules in
[Privacy requirements for Voter Notices](#privacy-requirements-for-voter-notices)
are intended to prevent that. In summary:

* a Wallet Application does not send any user-specific data in order to fetch,
  display, or report on a Voter Notice;
* a Voter Notice is shown to all users of the application in the same way,
  and is not targeted by balance, address type, or any other property of the
  user's wallet; and
* compliance reports under this ZIP do not include per-user data.

This ZIP adds a machine-readable Vote Notice Feed published by the Poll
Organizers. Fetching a static public file from a well-known URL reveals no
more than an ordinary update check, provided it is done without identifiers.
Wallet Applications can instead ship Voter Notices in an ordinary software
update, which reveals nothing new.


# Requirements

* Organizations funded by a Zcash Funding Source tell their End Users about
  each upcoming Coinholder Vote by reasonable means, including in-wallet
  notices where they publish a Wallet Application.
* Voter Notices are neutral, and do not collect or leak information about the
  user.
* Unfunded wallets and services can display the same notices easily if they
  choose to.
* Compliance is enforced through the grant agreements and disbursement
  schedules that the community already controls.
* The rules align with the Zcash Town Square ZIP [^draft-town-square] and the
  companion notice-period ZIP [^draft-notice-period].


# Non-requirements

* This ZIP does not set the notice period for a Coinholder Vote, or decide
  whether a vote is binding. Those are the subject of the companion
  notice-period ZIP [^draft-notice-period].
* This ZIP does not require any organization to support voting in its
  software. A Wallet Application that does not support voting still gives a
  Voter Notice, and says where the user can vote.
* This ZIP does not require any organization to take a position on any
  question, or forbid it from doing so outside a Voter Notice.
* This ZIP does not bind organizations that are not Funded Organizations, such
  as exchanges and independent wallets.


# Specification

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
a Material Change under the notice-period ZIP [^draft-notice-period], the Funded Organization MUST update its
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
"Voter Notice Kit", linked from the Notice of Vote, containing:

* a neutral one-sentence description of the vote, of no more than 25 words;
* a neutral short notice, of no more than 60 words; and
* a neutral long notice, of no more than 250 words,

each of which meets the [Content](#content) and [Neutrality](#neutrality)
requirements of this ZIP.

The Poll Organizers MUST also publish a machine-readable "Vote Notice Feed"
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
the Forum category for Notices of Vote designated under the notice-period ZIP
[^draft-notice-period].
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
substantial violation, it constitutes a failure to meet its Transparency
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
already controls. For the duty to inform End Users, the lever is the grant agreement and the
disbursement schedule. The notice-and-cure step keeps the consequence
proportionate. A wallet team that misses a release and fixes it promptly loses
nothing. Only an organization that refuses to inform its users, or uses a
Voter Notice to campaign or to collect data, has its disbursements suspended,
and only until it complies.
</details>

## Activation

This ZIP becomes effective when its Status becomes Active (the "Effective
Date"). It applies to every Coinholder Vote whose Notice Date is on or after
the Effective Date. For a Funded Organization whose grant agreement does not
yet include the condition in [Conditions of funding](#conditions-of-funding),
the duty applies as a SHOULD until its agreement is amended or renewed.

Funded Organizations are encouraged to comply voluntarily from the time this
ZIP is published as a Draft.


# Rationale

## Why place the duty on funded organizations

Organizations that receive money from a Zcash Funding Source are funded by the
protocol, and so by coinholders. Asking them to tell coinholders about votes
is a small and fair condition of that funding. It is also where the users
are: the main Zcash wallets are built by funded teams.

Unfunded organizations, such as exchanges and independent wallets, are not
bound, because a Process ZIP has no lever over them. The Voter Notice Kit and
Vote Notice Feed are designed so that they can display notices easily if they
choose to, and the Specification asks Poll Organizers to invite them.

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

## Why a separate ZIP

The notice period and the duty to inform users solve different problems and
impose very different costs. The notice period asks only the Poll Organizers
to wait, and costs nothing to adopt. The duty to inform asks every funded
organization to change its software and its communications. Keeping them
apart lets the community adopt the notice period quickly, and decide on the
duty to inform on its own merits.


# Open questions

* Should Funded Organizations that hold only small grants, or individual
  grantees with no products, be exempt from the duty to inform End Users?
* Should exchanges and custodians that are not Funded Organizations be invited
  to sign a voluntary commitment to display Voter Notices, and should the
  register record which have done so?
* Should this ZIP stay separate from the notice-period ZIP
  [^draft-notice-period], or be merged with it after community polling?


# References

[^BCP14]: [Information on BCP 14, "RFC 2119: Key words for use in RFCs to Indicate Requirement Levels" and "RFC 8174: Ambiguity of Uppercase vs Lowercase in RFC 2119 Key Words"](https://www.rfc-editor.org/info/bcp14)

[^zip-1015]: [ZIP 1015: Block Subsidy Allocation for Non-Direct Development Funding](zip-1015.rst)

[^zip-1015-transparency]: [ZIP 1015: Block Subsidy Allocation for Non-Direct Development Funding, Transparency and Accountability](zip-1015.rst#transparency-and-accountability)

[^zip-1015-enforcement]: [ZIP 1015: Block Subsidy Allocation for Non-Direct Development Funding, Enforcement](zip-1015.rst#enforcement)

[^zip-1016]: [ZIP 1016: Community and Coinholder Funding Model](zip-1016.md)

[^zip-1016-disbursement]: [ZIP 1016: Community and Coinholder Funding Model, Disbursement process](zip-1016.md#disbursement-process)

[^draft-mcgee-keyholders]: [Draft ZIP: Update to ZIP 1016 & ZIP 271: Key-Holder Organizations](draft-mcgee-keyholders-organizations.md)

[^draft-town-square]: [Draft ZIP: The Zcash Town Square: Official Discussion and Announcement Cross-Posting](draft-emersonian-zcash-town-square.md)


[^forum-timeline]: [Zcash Community Forum: "ZCG and the Dev Fund Timeline for Proposals and Polling", first post 2026-11-05, and replies to 2026-11-08](https://forum.zcashcommunity.com/t/zcg-and-the-dev-fund-timeline-for-proposals-and-polling/58906)

[^draft-notice-period]: [Draft ZIP: Update to ZIP 1016: Minimum 30-Day Notice for Coinholder Votes](draft-emersonian-coinholder-vote-notice-period.md)
