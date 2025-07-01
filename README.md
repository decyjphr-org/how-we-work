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

# Example Work Item Hierarchy: EHR Software 

# Alternative Work Item Hierarchy: Epic as Initiative

## Initiative 1: Patient Registration & Tracking

### Epic 1.1: Patient registration UI and API

#### Batch 1.1.1
- Build React.js patient registration forms (demographics, contact, ID proof)
- Implement Axios-based API calls to Node.js/Express backend
- Design patient registration REST endpoints in Node.js/Express
- Integrate patient data storage with EHRbase backend (via REST API)
- Persist patient records in PostgreSQL (Docker)

### Epic 1.2: Unique MRN generation logic

#### Batch 1.2.1
- Implement MRN generation algorithm in backend
- Store and retrieve MRNs via EHRbase/PostgreSQL
- Expose API endpoint for MRN assignment

### Epic 1.3: Visit/admission tracking (OPD/IPD)

#### Batch 1.3.1
- Create visit/admission tracking UI in React.js
- Implement Express endpoints for visit/admission events
- Store visit/admission data in EHRbase/PostgreSQL

### Epic 1.4: Consent forms and patient communications (Phase 2)

#### Batch 1.4.1
- Design digital consent form UI and APIs
- Store consent records securely (EHRbase/PostgreSQL)
- Implement patient communication templates and delivery logic

---

## Initiative 2: Notes & Diagnosis

### Epic 2.1: SOAP note templates & progress notes

#### Batch 2.1.1
- Develop React.js dynamic forms for SOAP notes (specialty-based)
- Create API endpoints for storing/retrieving notes (Express)
- Map SOAP notes to EHRbase compositions/entries

### Epic 2.2: Diagnosis entry with ICD-10

#### Batch 2.2.1
- Integrate ICD-10 code search/autocomplete in frontend
- Store diagnoses as structured data in EHRbase/PostgreSQL

### Epic 2.3: Procedure documentation

#### Batch 2.3.1
- Create UI for procedure documentation (e.g., surgeries, biopsies)
- Persist procedure records in EHRbase/PostgreSQL

---

## Initiative 3: Orders & Result Viewing

### Epic 3.1: CPOE (Computerized Physician Order Entry)

#### Batch 3.1.1
- Build React.js order entry forms (lab, imaging, meds)
- Implement order management APIs (Node/Express)
- Store orders in EHRbase/PostgreSQL

### Epic 3.2: Order sets and templates

#### Batch 3.2.1
- Allow creation and management of order sets/templates (UI + API)
- Store order sets as reusable entities in backend

### Epic 3.3: Lab/radiology result viewer

#### Batch 3.3.1
- Develop results viewer UI in React.js (structured + attachments)
- Fetch results from EHRbase and display attachments (images, PDFs)

---

## Initiative 4: Medications & Pharmacy

### Epic 4.1: Medication orders and scheduling

#### Batch 4.1.1
- Create medication order UI in React.js
- API for medication administration scheduling (Express)
- Store scheduling data in EHRbase/PostgreSQL

### Epic 4.2: eMAR, drug interaction, inventory linkage (Phase 2)

#### Batch 4.2.1
- eMAR UI and backend logic
- Drug interaction engine integration (backend)
- Inventory linkage APIs for pharmacy dispensation

### Epic 4.3: Injections, infusions, ad hoc medicines

#### Batch 4.3.1
- UI and backend for ad hoc medication entries

---

## Initiative 5: Nursing & Therapy

### Epic 5.1: Nursing notes and shift/task documentation

#### Batch 5.1.1
- UI for nursing notes (shift-wise, task-based)
- API and storage for nursing notes

### Epic 5.2: Vital signs charting, intake/output

#### Batch 5.2.1
- Implement charting UI (React.js) and backend endpoints
- Store vital signs and intake/output in EHRbase/PostgreSQL

### Epic 5.3: Therapy notes (Phase 2)

#### Batch 5.3.1
- UI and backend for physio, nutrition, speech therapy notes

---

## Initiative 6: Discharge & Follow-up

### Epic 6.1: Discharge summaries

#### Batch 6.1.1
- Generate discharge summaries (template-driven UI)
- Store/print summaries from EHRbase

### Epic 6.2: Referral, follow-up, CCD/FHIR (Phase 2)

#### Batch 6.2.1
- Referral and follow-up scheduling UI and backend
- CCD/FHIR resource generation for continuity of care

---

## Initiative 7: Interoperability

### Epic 7.1: HL7/FHIR, DICOM, ePrescription, HIE (Phase 3)

#### Batch 7.1.1
- FHIR API endpoints and mapping to EHRbase
- HL7 message processing in Node.js
- DICOM PACS integration module (backend)
- ePrescription API implementation (National Health Stack)
- Aadhaar, ABHA ID integration (backend + frontend)
- Health Information Exchange (HIE) secure API layer

---

## Initiative 8: Security Features

### Epic 8.1: RBAC, audit trails, consent, encryption

#### Batch 8.1.1
- RBAC implementation (roles/permissions in backend)
- Audit trail logging (read/write) in Express/Node.js
- Consent management UI and backend (Phase 2)
- Encryption at rest (PostgreSQL) and in transit (HTTPS)

### Epic 8.2: HIPAA/NABH/NDHM (Phase 3)

#### Batch 8.2.1
- HIPAA/NABH/NDHM documentation and gap analysis
- Compliance enforcement in API, database, and logging

---

## Initiative 9: Clinical Analytics

### Epic 9.1: Dashboards & Tracking

#### Batch 9.1.1
- Clinical dashboards (React.js + backend API)
- Backend aggregation for outcomes, infections, etc.

### Epic 9.2: Alerts & Predictive Tools (Phase 2)

#### Batch 9.2.1
- Alerting system (drug interactions, critical labs)
- Predictive analytics (readmission risk) engine
- Resource utilization tracking (backend + dashboard)

---

**Legend:**  
- *Initiative*: Major functional area  
- *Epic*: Sub-area or core subdomain  
- *Batch*: Group of closely-related deliverables  
- *Task*: Smallest actionable unit, broken down by stack: React.js (frontend), Axios/API, Node.js/Express (API), EHRbase (backend), PostgreSQL (DB)
