# How we organize our planning and tracking process.


## Work Items
- Initiative
- Epic
- Batch / Feature
- Task
- Bug
- Spike

## Work Item States (Status)
- New
- Backlog
- Ready for work
- In progress
- Icebox
- Done
  
### Special states for Epics and Initatives
- Preview
- GA

## Trending States
- Inactive
- On track
- At risk
- Off track
- Done
  
## Where to track work items
Initially we will track all work items in the same repo as the code is.

As we evolve, Tasks and Batches(Features), and would be usually confined to one repo and so will be tracked in the repo where the code is.

Epics and Initiatives would evolve into multiple product lines and mutiple repos. We might also want to isolate non-tech folks from low-level information and stakeholders may be scattered across multiple repos and teams and elsewhere. Centralizing conversation and context will pay dividends for the DRI and other stakeholders for the lifetime of the body of work.

If the epic is a part of an overarching initiative, find that initiative and add a link to the epic. This will keep all initiative stakeholders aligned.

## Initiative Workflow

Typically a quarter (or more) long, Initiatives are the largest grouping of work and are composed of multiple efforts typically around a unified theme or goal. Ideally an initiative serves as a complete tracking issue for getting a project from 0 to completely done, linking to all key epics and batches that exist independent of epics, and is focused on high levels goals and strategy.

An initiative issue is a great place to have a conversation that doesn't quite fit in any of the existing epics and batches.

Initiatives are broken down into multiple epics, normally by the product and engineering leads, managers of managers (M2s) and managers of independent contributors (M1s), although anyone can be included in this break down.

Each Initiative has a Directly Responsible Individual (DRI), Generally a Product Manager (PM) or Engineering Manager (EM).

The workflow is simple.

- The Initiative DRI posts status reports as needed to communicate key changes on the initiative's health, reports on progress towards Key Results, and on completion of the initiative.

Examples of initiatives:
- REST API for Patient Management Module
- Stable hosting of EHR back-end


## Epic Workflow

Typically around 4 to 6 weeks long (time to be engineering-done), composed of multiple batches. Ideally an Epic completes some bit of meaningful work and can stand on its own.

Epics are just a best guess at portions of the work it will take to complete initiatives. The epics should have a clear exit criteria of done. The epic backlog should be an ordered list that is constantly being prioritized.

Leadership team breaks down __epics__into __batches__ (aka features), creating what we think might be the batches needed in order to complete the epic.

Teams start __epics__ that are prioritized and ready for work (assigned). Once an __epic__is assigned and in progress the general workflow is:

- The Epic DRI works with team members to determine a target date
- The Epic DRI posts reports each week at an agreed upon time
- The Epic DRI does the Acceptance testing once the status is in `Done`
- The Epic DRI will change the status to `Preview` or `GA`
- Upon completion meeting the agreed upon exit criteria, the Epic DRI should share a final update to the stakeholders (via WhatsApp, or similar) that the epic has been completed that includes a demo/screenshots of the epic and any other pertinent information.

Examples of Epics:
- Patient registration
- Visit/Admission Tracking

## Batch Workflow
Typically around a few days to maximum two weeks of work to be engineering-done.

A “batch” is a piece of work that is significant enough to capture meaningful progress or value, while being small enough to complete relatively quickly by a single engineering team.

The batch backlog should be constantly prioritized. Even when  multiple people are working in parallel, we still prioritize the list. Its ok for persons to have affinity to work and not just take the next thing. What work a person picks up next is decided by the Leadership Team. When a team/person completes a __batch__ and is ready to pick up work, the most common order would be to first see if any other teams/persons need help finishing in-flight batches, second they might pick up "Other" work not associated with an __Epic__ and finally they would look to pick up the next __batch__ in the __Epic__ to which that person is assigned.

To transistion a __batch__ from `backlog` to `ready for work` the general workflow is:

- Assignees will take a day or two to plan out the batch. The batch is planned by building out tasks that are each about a day's worth of work. These tasks are added to a board with the status as `Ready for work`.
- If needed, a technical design should be created which includes key architectural and technical decisions documented with an Architecture Decision Record.
- The team sets a target date that they believe it will be done by. If this target date is longer than 2 weeks out, the team should go back to discuss if they should still proceed or if the work should be reconsidered, or broken down more.
- The Batch DRI communicates any changes during the execution of the batch, such as unexpected issues or a revised target date.
- The Batch DRI will do the Acceptance testing and mark the status as `Done`
- Upon completion meeting the agreed upon exit criteria, the Batch DRI should share a final update to the organization (via WhatApp) that the batch) has been completed that includes a demo/screenshots of the batch and any other pertinent information.


- A __batch__ will be merged to the parent branch when it is done. Batch from an Epic will be merged to the Epic, but`standalone`  __batch__ will be merged to `main` .

## Task Workflow
Use their best judgment for small bugs and improvement tasks. 

If you are working in an area and there are small (< 2 hours) fixes to make, just do it. If you are somehow blocked or just need a break and want to pick up a small bug to fix, do it.

Similarly for engineering improvements, if the team agrees that it’s important and doesn’t significantly impact the committed work the team has already taken on, do it.

For urgent issues, do the right thing: mitigate live-site issues, unblock broken builds and failing deployments.

Also - if you find an issue that's blocking you completing your current in-flight work, and it's something you can fix, just fix it - it's part of that work item.

All bugs estimated to take longer than a day can be saved and bundled together in a __batch__. Larger bugs (2+ days) can also become their own __batch__ and get prioritized alongside other __batch__ work. The key is to keep the work visible.

## Attributes of a work item
- Title
- Description
- Status
- Assignees
- Priority
- Start Iteration / Start Week
- End Iteration / End Week
- Effort Estimate (# of iterations)
- Issue Type
- Area
- Size

## Work Item Visibility

We should have a way to isolate and view each of the core __work items__ , their priorities in relation to one another, and their various stages.

