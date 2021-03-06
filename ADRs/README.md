# Architecture Decision Records

# Purpose

**TODO**

# Process

<!-- Can be Proposed, In Progress, In Review, Accepted, Rejected, Deferred or Superseded -->
Logically an ADR can be in a number of states (Proposed, In Progress, In Review, Accepted, Rejected, Deferred or Superseded) with the following state machine

```
<start> ----> Proposed
   |              |
   |              V
   +--------> In progress
                  |
                  V
              In review
                  |
                  V
Deferred <--> Accepted --> Rejected
                  |
                  V
              Superseded
```

However, to avoid tracking these states directly in the ADRs themselves it makes sense to use the Github PR workflow as much as possible.

## Proposed

We need the proposed state because the need for an ADR might be identified before anyone is able to work on it (or before the right author has been identified).

A _Draft PR_ is opened with draft "Context and Problem Statement" section. 
The PR is labeled with `Proposed`.

When an author has been identified and ready to work on the ADR is transitions to "In progress".

# In progress

In this state the ADR is being elaborated by an author(s).

Any `Proposed` label is removed from the draft PR when it's being worked on.

When the author thinks the ADR is ready for review it transitions to "In review".

## In review

The author changes the _Draft PR_ to a _Ready for review PR_ in github. 
The relevant stakeholders are tagged for review.
Other people may also review the PR.
Reviewer approval or rejection is signalled using the github UI.

There are four possible outcomes:
* If changes are requested the authors should make them, as part of the normal github PR process.
* Transition to the Accepted state, signalled by reviewer approval of the PR using the github UI.
* Transition to the Rejected state, signalled by reviewer rejection of the PR using the github UI.
* Transition to the Deferred state, signalled by reviewer approval of the PR using the github UI.

## Accepted

The ADR's PR is merged.

Most ADRs will remain in this state, but some might later transition to "Superseded".

## Rejected

The ADR's PR is labelled with `Rejected` and closed.

## Deferred

The ADR's PR is labeled with `Deferred` and left open.

## Supersedure

Rarely one ADR will supersede another. In this case
* the superseding ADR's PR should also update the ADR document of the superseded ADR to say that's superseded and link to the superseding ADR. 
* the superseding ADR document should note in the Context section which ADR is supersedes.

When a superseding ADR PR is merged, the superseded ADRs PR should retrospectively be labelled with `Superseded`.
