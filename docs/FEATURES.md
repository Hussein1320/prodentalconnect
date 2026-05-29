# ProDentalConnect — Feature Reference Guide

**Audience:** Practice staff and administrators  
**Version:** Current (Growth Plan)  
**Last updated:** May 2026

---

## 1. Overview — What is ProDentalConnect?

ProDentalConnect is a cloud-based dental practice management platform built for UK dental practices. It covers the full patient journey — from online booking and appointment management through to NHS claims, clinical charting, team communications, and revenue recovery — all in a single application.

The platform is split into two interfaces:

- **Staff App** — accessed by reception, dentists, hygienists, managers, and owners through a browser.
- **Patient Portal** — a mobile-friendly web page patients use to manage their own care (see Section 9).

---

## 2. Getting Started

### Login & Authentication

Staff log in with a username (or email address) and either a password or a numeric PIN. Super Admins must also complete a **two-factor authentication (2FA)** step using an authenticator app code.

SSO login is also supported via **Google** or **Microsoft** accounts — staff select their provider, authenticate with their work account, and the system matches them to their ProDentalConnect user record.

- **Role:** All staff
- **Key interactions:**
  - Username/email + password login
  - Quick PIN login (4+ digit numeric code)
  - Google Workspace / Microsoft Entra SSO
  - 2FA code entry (Super Admin only)
  - "Forgot password" flow

### User Roles

The system has six roles. Each role determines which sidebar items are visible and which actions are permitted.

| Role | Who it is | Typical access |
|---|---|---|
| **Reception** | Front desk staff | Calendar, Patients, Messaging, NHS Claims, Accounts |
| **Dentist** | Treating dentist | Clinical tools, Charting, FP17, Notes, Calendar |
| **Hygienist** | Dental hygienist | Charting, Clinical Notes, Calendar |
| **Manager** | Practice manager | Full practice access excluding super-admin tools |
| **Practice Owner** | Owner | Same as Manager |
| **Super Admin** | ProDentalConnect system admin | Platform-wide administration across all practices |

Managers can further restrict or expand individual staff permissions within their role defaults (see Section 8 — Users).

---

## 3. Dashboard

**Role:** Reception, Dentist, Hygienist, Manager, Owner

The dashboard is the first screen after login and shows a personalised view depending on the logged-in user's role.

- **Personalised greeting** — shows the user's name, role status, and how many patients are in the waiting room.
- **KPI tiles** — four headline figures for the selected date range: Completed appointments, Cancelled appointments, DNAs (did-not-attend), and Remaining appointments. Clicking any tile opens a drill-down list of patients in that category.
- **Date range selector** — filter KPIs by Today, Yesterday, Last 7 days, Last 30 days, Last 90 days, or a custom range.
- **Smart Insight Banner** — AI-generated nudges highlighting actions such as overdue recalls, low UDA progress, or revenue at risk.
- **Practice Health Gauge** — compact visual score (0–100) reflecting operational health across multiple dimensions.
- **Operational Intelligence Card** — highlights anomalies such as appointment pressure, diary gaps, or staff utilisation issues.
- **Diary Pressure Strip** — visual summary of today's appointment load by surgery.
- **Weekly Pulse Widget** — trend indicators across the rolling 7-day period.
- **Waiting room quick-view** — real-time count of patients currently waiting, with a direct link to the Waiting Room page.

---

## 4. Front Desk Modules

### 4.1 Daily Priorities (NBA — Next Best Action)

**Role:** Reception, Dentist, Hygienist, Manager, Owner

The Daily Priorities page surfaces AI-generated actions ranked by urgency and revenue value. Each action is tailored to the logged-in user's role.

- Urgent and standard actions displayed separately, each with an estimated value (£)
- Actions include: call back patients with outstanding treatment plans, contact overdue recalls, follow up on cancellations and DNAs, fill diary gaps
- One-click action: opens the relevant patient record or navigates directly to the related module
- Mark actions as done; dismissed actions are removed from the list
- **Total value at stake** shown at the top — the sum of revenue that could be recovered or converted

---

### 4.2 Morning Huddle

**Role:** Reception, Manager, Owner

A pre-session briefing tool designed for the start-of-day team meeting. Displays the full day's appointment schedule in a structured, clinical-alert-focused layout.

- Full appointment list with time, patient name, treatment type, dentist, and confirmation status
- **Alert flags per appointment:** DNA history count, outstanding balance, clinical alerts (e.g. Warfarin/INR requirement, anxious patient, new patient forms needed)
- Outstanding tasks carried over from the previous day (callbacks, lab chases, payment follow-ups, referrals)
- **Gap detection** — available diary slots highlighted so the team can proactively fill them
- **Short-notice patient list** — patients opted in to be contacted for last-minute slots shown directly in the huddle view
- Send appointment reminders directly from this page
- Mark tasks as done with one click

---

### 4.3 Calendar

**Role:** Reception, Dentist, Hygienist, Manager, Owner

The multi-column appointment diary, one column per dentist/surgery.

- **Day view** — 5-minute time-slot grid with colour-coded appointments by treatment type
- **Drag and drop rescheduling** — appointments can be dragged to a new time slot; conflicts are checked automatically
- **New appointment booking** — click any free slot to open the booking form (patient, treatment type, duration, dentist, reason, notes)
- **Edit appointment** — click an existing appointment to open a context panel; edit all fields or delete the appointment
- **Appointment context panel actions:**
  - Mark as arrived / check in patient
  - Send a reminder (SMS/WhatsApp) with customisable message
  - Add a note to the appointment
  - Request a digital consent form signature (e-signature workflow)
  - Mark as DNA — triggers the DNA workflow
  - Open the patient record
- **Staff leave conflict detection** — the calendar checks approved leave data and warns when a dentist has approved leave on the selected date
- **Appointment colour coding** by treatment type (Check-up, Filling, Crown, Extraction, Hygiene, Implant, Consultation)

---

### 4.4 Waiting Room

**Role:** Reception, Dentist, Hygienist, Manager

Real-time waiting room management board.

- **Live timer** per patient from the moment they checked in, colour-coded green → amber → red based on a configurable threshold (default: 20 minutes)
- **Emoji face indicator** that reflects patient wait time relative to the threshold
- **Tabs:** Waiting Now | Full Daily Schedule
- **Manual check-in** — staff can manually add a walk-in patient by name and dentist
- **Call in patient** — one-click action notifies the dentist the patient is ready; changes the patient status from "waiting" to "called"
- **DNA workflow** — mark a patient as DNA directly from the waiting room; this triggers a configurable outreach sequence (reminder message, rebooking prompt)
- **Wait threshold setting** — managers can adjust the alert threshold (minutes) from within the page
- **Undo last DNA marking** — a brief undo window after marking a patient as DNA

---

### 4.5 Patients

**Role:** Reception, Dentist, Hygienist, Manager, Owner

The main patient list and search screen.

- Search by patient name or email address (live filter)
- Filter by patient type: All | NHS | Private
- Columns: Patient name, Date of birth, NHS number, Assigned dentist, Next appointment, Outstanding balance, Clinical flags
- Click any patient row to open the full **Patient Record** (see Section 5)
- **Add Patient** button opens a form to register a new patient directly

---

### 4.6 Online Booking

**Role:** Reception, Manager, Owner

Manages the practice's patient-facing online booking configuration and incoming booking requests.

- View and respond to incoming online booking requests from patients
- Configure available appointment types, durations, and which dentists accept online bookings
- Set booking availability windows and lead times
- Booking requests require staff confirmation before appearing as confirmed appointments in the calendar

---

## 5. Patient Record

**Role:** Reception (limited tabs), Dentist, Hygienist, Manager

Each patient has a detailed multi-tab record. The tabs displayed depend on the logged-in user's role; dentists see clinical tabs first, reception sees admin tabs first.

### Available Tabs

#### Details
Core demographic and administrative information. All fields are inline-editable with every change logged to the audit trail.

- Name, preferred name, date of birth, gender, ethnicity, occupation
- NHS number, GDC number, NI number, insurance number/insurer
- Contact details: mobile, home phone, work phone, email
- Address
- Assigned dentist and hygienist
- Patient type (NHS/Private), NHS evidence status
- Recall intervals (dentist and hygienist, configurable in months)
- Next recall due dates
- GP details (name, surgery, contact)
- Referral source and specialist details
- Communication preferences: SMS/email marketing, recall method
- **Family linking** — group family members under a shared family ID; add/remove family members
- Acquisition source
- **GDPR / Deletion requests** — staff can request deletion of specific fields or the entire record; requests are sent to the manager for approval

#### Activity
A chronological feed of all interactions with this patient: appointment history, messages sent, balance changes, clinical alerts raised, documents sent.

#### Chart (Dentist/Hygienist/Manager only)
The interactive dental chart (odontogram).

- **Odontogram view** — interactive full-mouth tooth diagram for marking conditions and treatments on individual teeth
- **Voice charting** — microphone input lets the dentist dictate tooth conditions and treatments using voice commands, which are parsed and applied to the chart automatically
- **BPE (Basic Periodontal Examination)** scoring grid
- Perio charting panel with pocket depth and bleeding point recording
- Treatment plan builder — select teeth and treatments; costs calculated automatically
- Mark tooth conditions: caries, restoration present, missing, crowned, implant, root canal, fracture, watch

#### Medical History (Dentist/Hygienist/Manager/Reception)
Configurable medical history questionnaire. Questions are set up in Settings → Medical History Questions.

- Toggle yes/no for each medical condition (e.g. blood thinners, asthma, diabetes, penicillin allergy, heart conditions)
- Conditional follow-up fields appear when a condition is flagged positive (e.g. medication name, dose, prescribing doctor for anticoagulants)
- Social history: cigarettes per day, alcohol units per week, vaping status
- Clinical override note field for additional observations
- Every save is logged with date, time, and the staff member who saved
- **NHS Scotland Additional Support Needs (ASN) marker** — toggle visible to eligible practices

#### Appointments
Full appointment history for this patient, with status indicators (booked, completed, DNA, cancelled).

#### Clinical Notes (Dentist/Hygienist/Manager)
Structured and free-text clinical note entry linked to appointment dates.

- **AI Note Assistant** — AI drafts a structured clinical note based on the treatment recorded, which the clinician can review, edit, and finalise
- Notes display as a chronological list; each note shows date, dentist, and the note content
- Notes can be finalised (locked) once signed off

#### Treatment Plans (Dentist/Manager/Reception)
View and manage treatment plans associated with this patient.

- List of proposed and accepted treatment items with costs
- NHS band calculation
- Accept/decline workflow; accepted plans sync with the patient portal for patient sign-off
- Finance options can be offered inline (Chrysalis, payment plan)

#### Accounts (Reception/Manager)
Financial summary for this patient.

- Outstanding balance and overdue status
- Line items (treatments billed, amounts, NHS band)
- **Take payment** — send a Stripe payment link, initiate a card reader payment, or mark as paid manually
- **Send payment reminder** — send SMS reminder with outstanding amount

#### Documents
Manage documents associated with this patient.

- List of saved documents (treatment reports, invoices, consent forms, aftercare leaflets)
- **Send document** — email a document to the patient; the send log records who sent it and when
- **Encrypted report sending** — option to send reports with an encryption layer (if enabled by manager)
- **Treatment Report modal** — generate a structured treatment report PDF covering treatment completed, recommended next steps, and costs

#### History / Audit Log (Manager/Dentist)
Immutable audit trail of all changes to this patient record: which field changed, old value, new value, who made the change, and when.

#### Consent Forms (Dentist/Manager/Reception/Hygienist)
Manage consent forms for this patient.

- View previously signed general consent forms
- Send a new consent form to the patient (by email or via the patient portal)
- **Sign in-practice** — staff can record in-practice consent with digital signature capture
- Forms are stored and time-stamped against the patient record
- In-practice e-signature capture for patients attending the surgery

---

## 6. Clinical Modules

### 6.1 Clinical Notes

**Role:** Dentist, Hygienist, Manager, Owner

Standalone clinical notes page (separate from the patient record tab) for browsing and creating notes across all patients.

- Search and filter notes by dentist, date range, and patient
- Create new clinical notes linked to a patient and appointment
- AI Note Assistant available for note drafting (same as within the patient record)
- Notes must be finalised before they can be submitted or shared

---

### 6.2 X-Ray Imaging

**Role:** Dentist, Manager, Owner

IRMER-compliant X-ray justification and reporting log.

- Log new X-ray exposures with: patient, X-ray type (Bitewings, PA, OPG, CBCT), date, dentist, clinical justification, and report/findings
- View the full log of all X-rays taken
- Open image viewer (links to imaging system)
- All entries include the justification text to demonstrate IRMER compliance

---

## 7. NHS Modules

### 7.1 FP17 Claims

**Role:** Dentist, Reception, Manager, Owner

NHS England, Scotland, and Wales FP17 claim management.

- **Claim list** with status filters: All | Draft | Submitted/Accepted
- **ASN filter** (NHS Scotland Additional Support Needs claims)
- **Free Repair/Replacement filter** (England/Wales)
- **Continuation claim flag**
- **New FP17 form** — create a draft claim with:
  - Patient search with live autocomplete from the patient database (or register as new patient)
  - NHS number (auto-filled from patient record)
  - Dentist, date, NHS region (England/Scotland/Wales), claim type (treatment/capitation), band (1/2/3)
  - ASN marker, continuation claim marker
  - Treatment items with NHS fee, patient fee, and free repair/replacement status per item
  - UDA count auto-calculated from the band selected
- **Review and edit** submitted/draft claims
- **Submit claim** to BSA (Compass)
- Claim statuses: Draft → Submitted → Accepted

#### Extended NHS Tools (NHS menu items accessible depending on practice contract region)
The following specialist NHS pages are available for practices with the relevant regional contracts:

- **UDA Tracker** — NHS contract year UDA progress by dentist (see Section 7.2)
- **NHS Wales Claims** — Wales-specific claim workflow (see Section 7.3)
- **NHS Reconciliation** — reconciliation against BSA payment schedules (see Section 7.4)
- **NHS England Apr 2026** — new contract compliance tools (see Section 7.5)
- **NHS Wales Advanced** — ACORN, CP Engine, Lab Fee, Referral, and Incomplete Work workflows (see Section 7.6)
- **NHS CDS Compliance** — CDS submission and compliance checking (see Section 7.7)
- **NHS Denture Repair** — denture repair claim workflow (see Section 7.8)
- **NHS Northern Ireland (NI)** — NI-specific claim management (see Section 7.9)
- **NHS UDA Report** — detailed UDA/UOA activity export and forecasting (see Section 7.10)
- **NHS Claim Compliance** — cross-region claim compliance checking (see Section 7.11)
- **NHS Wales CP Engine** — Wales Care Package real-time calculation (see Section 7.12)
- **NHS Wales ACORN** — dynamic ACORN clinical assessment forms (see Section 7.13)
- **NHS Wales Lab Fee** — NHS vs Private lab fee management (see Section 7.14)
- **NHS Wales Referral** — urgent and advanced referral claim system (see Section 7.15)
- **NHS Wales Incomplete Work** — prep-only eligibility and package downgrade engine (see Section 7.16)
- **NHS Regional Routing** — route claims to correct regional BSA gateway (see Section 7.17)
- **NHS Enterprise** — multi-contract management including orthodontics and Scotland (see Section 7.18)
- **NHS Regional Architecture** — infrastructure configuration for multi-site NHS setups (see Section 7.19)

---

### 7.3 NHS Wales Claims

**Role:** Dentist, Reception, Manager, Owner  
**Region:** Wales practices only

Wales-specific FP17 (WP17) claim management using NHS Wales Care Packages. Replaces the standard band-based claim model for practices under a Welsh NHS contract.

- Claim list with status filters (Draft / Submitted / Accepted / Rejected) and Care Package filter
- Each claim records: patient, NHS number, dentist, contract, treatment start/end dates, ethnicity, exemption, and Care Package assignment
- **Care Package auto-mapper** — automatically assigns the correct Wales Care Package (CP1–CP4, CPE, etc.) based on treatment codes added to the claim
- **Validation engine** — pre-submission checks for: missing ethnicity, missing Care Package, missing contract, missing treatment end date, and contract region mismatch
- Submit claim to WebEDI (NHS Wales gateway); claim status progresses from Draft → Submitted → Accepted
- Full **audit log** per claim recording each change, user, and timestamp
- New claim form with patient search, treatment item builder, NHS fee and patient fee per item, and free repair/replacement status
- Prompt on submission to close the course of treatment if complete

---

### 7.4 NHS Reconciliation

**Role:** Dentist, Reception, Manager, Owner

A "Reconciliation Command Centre" that connects NHS claims, BSA payments, practitioner allocations, and outstanding issues in one view.

- **KPI summary strip:** Completed NHS value, submitted value, BSA-approved value, paid to practice, outstanding, rejected, underpaid, unallocated, and open issues count
- **Issues tab** — list of reconciliation discrepancies: unpaid claims, rejected claims, missing claims (treatment with no FP17 submitted), underpaid claims, unallocated income, BSA-adjusted values, and period mismatches; filterable by practitioner, severity, and issue type
- **Payments tab** — BSA payment records matched against submitted claims; highlights matched, underpaid, unallocated, and adjusted payments
- **Practitioner Allocation tab** — income breakdown per clinician: completed value, submitted, approved, paid, rejected, adjustments, and net
- **Audit tab** — log of all reconciliation actions taken by staff with user, timestamp, and reason
- Per-issue actions: add internal note, mark resolved, query with BSA, export issues to CSV
- "Reconcile Now" button triggers a full re-run of the reconciliation against current claim data
- Date range filter for flexible period-by-period analysis

---

### 7.5 NHS England Apr 2026

**Role:** Dentist, Reception, Manager, Owner  
**Region:** England practices only (from 1 April 2026)

Compliance tooling for the April 2026 NHS England contract changes, covering four new remuneration and category rules.

- **Unscheduled Care tab** — mark emergency appointments as Unscheduled Care; activity credit (£60) and slot credit (£15) are applied automatically and shown as KPIs; failed-attendance flag tracks DNA status
- **Nurse-Led Fluoride Varnish tab** — configure NHS nurses as eligible FV practitioners; validation rules enforce that only eligible FV treatment codes can be claimed under NHS Nurse role, and only for patients under 16
- **Band Updates tab** — fissure sealants now classified as Band 2 (not Band 1); the page surfaces any existing claims using the old classification and flags them for review
- **Denture Migration tab** — deprecated denture category codes (405, 407) are detected across existing records and a migration path to the replacement codes is provided
- **Reporting tab** — summary metrics: Unscheduled Care claims count, activity credit total, nurse-led FV claims, Band 2 fissure sealants, deprecated category usages
- Header KPI strip shows all five metrics at a glance with colour-coded tiles

---

### 7.6 NHS Wales Advanced Care Package Workflows

**Role:** Dentist, Reception, Manager, Owner  
**Region:** Wales practices only (from 1 April 2026)

Advanced NHS Wales workflow pages covering eight specialised areas of the April 2026 Wales contract catalogue.

- **Apr 2026 Catalogue tab** — searchable table of all NHS Wales treatment codes with: code, description, Care Package assignment, Prep-Only flag, NHS Note flag, and CDS-only flag; auto-include codes for Stabilisation packages are highlighted; deprecated codes show replacement
- **Prep-Only tab** — lists treatments that generate a full Care Package on preparation alone (Crown, Bridge, Onlay, Veneer, anterior and posterior RCT); fitting appointment completes the package; multiple instances of the same Care Package are supported
- **NHS Note tab** — explains and lists NHS Note category (code W9399): treatments recorded for clinical completeness but excluded from Care Package calculation, claim payload, and patient charge; does not generate a Miscellaneous Care Package
- **Warranty tab** — manages warranty eligibility per treatment; warranty-related replacements are excluded from lab fee NHS claims
- **Lab Fees tab** — NHS vs Private lab fee split per treatment item; tariff validation against NHS Wales limits; HC3 exemption logic
- **Urgent Referral tab** — urgent referral flag (DAP) per course of treatment; marks the claim as Urgent Care Package (CPE) with the associated remuneration
- **Stabilisation tab** — auto-includes four specific SNOMED codes in Stabilisation packages; tracks stabilisation plan items
- **Reporting tab** — summary of all advanced workflow activity by category

---

### 7.7 NHS CDS Compliance

**Role:** Dentist, Reception, Manager, Owner

Enforces the transition from deprecated "Other Treatment" (OT) codes to the new CDS treatment codes (9380–9383) introduced by NHS England and Wales, with two enforcement phases: Warn (from August 2025) and Blocking (from November 2025).

- **CDS Migration Assistant tab** — lists all historical records using deprecated OT codes; shows patient, date, description, and the suggested CDS replacement code (9380, 9381, 9382, or 9383); "Migrate" button per item logs the migration to audit; "Migrate All" bulk action
- **New CDS Codes tab** — reference list of codes 9380–9383 with descriptions and applicable regions
- **Obturator Detection tab** — automatically classifies full upper acrylic dentures applied to zero teeth as obturators (code 9309); flags cases for review where classification is ambiguous
- **Validation Rules tab** — displays the active enforcement rules per region
- **Reporting tab** — counts of deprecated usage, pending migrations, completed migrations, obturator detections, and unresolvable codes
- Status banner at top of page shows current enforcement mode (Warn or Blocking) and date

---

### 7.8 NHS Denture Repair

**Role:** Dentist, Reception, Manager, Owner  
**Region:** England and Wales

Dedicated claim workflow for denture repair (Band 0) ensuring correct Course of Treatment routing, automatic UDA allocation, and zero patient charge.

- Claim list with CoT routing status: attached to existing Band 3 CoT, separate repair claim (for Band 1/2 CoT), or new Band 0 claim (no open CoT)
- **New Denture Repair form** — patient name, repair component type (Clasp, Tooth, Flange, Other), and region (England/Wales)
- Automatic rules applied on creation: Band 0 non-banded, patient charge £0 (always free), 1 UDA auto-allocated, CoT routing determined by existing open courses of treatment
- KPI tiles: total repair claims, attached to Band 3 CoT, separate repair claims, new Band 0 claims, total UDAs allocated, patient charges raised (always £0)
- Full audit log per claim recording every system decision and manual change
- Tabs within the claim list: Claims | CoT Routing | Audit Log

---

### 7.9 NHS Northern Ireland

**Role:** Dentist, Reception, Manager, Owner  
**Region:** Northern Ireland practices only

NHS Northern Ireland (HSC) claim management including Panel Number management, Tier Amount configuration, and Prior Approval workflows.

- **Panel Numbers tab** — manage per-practitioner NI Panel Numbers and PINs; each practitioner can hold multiple panel numbers with labels (Main, Locum, Emergency Contract); set a default panel number per practitioner; enable or disable individual panel numbers; full audit trail per number
- **Tier Amount & Prior Approval tab** — configure the Tier Amount per practitioner (treatment value above which Prior Approval is required before claiming); claims exceeding the Tier Amount are flagged automatically; Prior Approval modal to submit, track, and update approval status (Awaiting / Approved / Rejected); claims linked to HCN/CHI patient identifier
- NI claim list showing: patient, practitioner, panel number label, claim value, tier amount, tier exceeded status, and prior approval status
- Add, edit, disable, and audit panel numbers from within the page
- Panel selector on each claim allows staff to choose which panel number to use for a given claim

---

### 7.10 NHS UDA Report

**Role:** Dentist, Manager, Owner

Detailed UDA and UOA (orthodontic) performance reporting with contract-level analytics and year-end forecasting.

- Toggle between UDA and UOA activity views
- **KPI strip:** contract target, achieved (by treatment plan completion date), submitted to BSA, progress percentage, forecasted year-end, and forecast variance (green if on/over target, red if behind)
- **Practitioner Performance table** — per clinician: UDAs/UOAs completed, submitted to BSA, number of claims completed, average per claim, and contract target with a visual progress bar
- **Contract table** — each NHS contract with annual UDA/UOA target, achieved to date, submitted, and region
- **Claim Status breakdown** — counts and UDA values by status: Completed, Submitted, Queued, Queried, Error
- **Monthly trend chart** — UDAs completed and submitted per month vs monthly target
- Filters: date range (by treatment plan completion date, not submission date), practitioner
- Activity counts by treatment plan completion date (not submission date) — clearly labelled
- Export to CSV

---

### 7.11 NHS Claim Compliance

**Role:** Dentist, Reception, Manager, Owner

A comprehensive NHS Claim Compliance Centre covering invalid claims, queried claims, XML diagnostics, contract tenure, overlap detection, location IDs, treatment validation, continuation eligibility, performer PINs, and SQ indicators — across all NHS regions.

- **Invalid Claims tab** — list of claims rejected by BSA with error detail; filter by practitioner and error category; drill into each claim to see all validation errors and actions (fix, resubmit, mark resolved)
- **Queried Claims tab** — BSA-queried claims with resolution status; accept adjusted value or dispute
- **XML Diagnostics tab** — input patient and contract details; run pre-submission XML validation check; flags XML-unsafe characters, postcode format errors, missing contract number, encoding issues; shows risk score (Low/Medium/High)
- **Contract Tenure tab** — validate claim dates against contract start/end dates
- **Overlap Detection tab** — test a date range for overlapping claims; flags courses of treatment that overlap a given period
- **Location IDs tab** — flags active NHS contracts without a Location ID assigned; shows count of missing IDs
- **Treatment Validation tab** — validates treatment codes per region rules
- **Continuation Validation tab** — tests whether a claim qualifies as a continuation (same patient, same contract, same or higher band, within 2-month window)
- **Performer PIN tab** — shows PIN status per practitioner (active, verified, missing); flags missing PINs
- **SQ Indicator tab** — manages SQ (sequence) claim indicators for replacements; validates whether the original claim was in an Acknowledged state before an SQ REPLACE can be used
- **Reporting tab** — summary metrics across all compliance categories

---

### 7.12 NHS Wales Care Package Engine

**Role:** Dentist, Reception, Manager, Owner  
**Region:** Wales practices only

Real-time NHS Wales Care Package calculation engine embedded within the treatment plan view, providing live fee calculation as treatments are added, removed, or completed.

- Displays the full treatment plan with items per appointment, each linked to a Care Package
- **Real-time auto-calculation** — Care Packages are calculated instantly as items are marked done; patient charge and practice fee update live
- **Urgent Referral (DAP) toggle** — marks the course of treatment as an Urgent Referral; triggers the Urgent Care Package (CPE) and associated remuneration
- **Transitional pricing detection** — plans started before 1 April 2026 are identified and priced under the transitional rules
- Claim settings per plan: Continuation flag, Treatment on Referral flag, Regulation 11 percentage reduction
- Exemption status banner if no NHS exemption is associated with the course of treatment
- Lab fee display — NHS lab fees linked to treatment items shown per Care Package
- Submit Care Package Claim button

---

### 7.13 NHS Wales ACORN Assessment System

**Role:** Dentist, Reception, Manager, Owner  
**Region:** Wales pilot practices

Dynamic ACORN (clinical assessment) form system for NHS Wales pilot practices. Allows creation, management, completion, and submission of ACORN-compliant clinical assessments.

- **Templates tab** — list of ACORN assessment templates with version, field count, region, and active/inactive status; activate the current template for use across the practice
- **Complete Assessment tab** — structured multi-section form dynamically rendered from the active ACORN template; field types include dropdowns, checkboxes, text, number, and textarea; required field validation; save as draft or submit
- **History tab** — log of previously completed assessments with patient, date, template version, status, and practitioner
- **Import Template tab** — import a new ACORN template from JSON; validates structure before activation; keeps historical templates for reference; supports pilot v2 templates
- **Reporting tab** — assessment completion and submission metrics
- JSON-based template format supports NHS Wales pilot versioning (v1.0, v2.0, etc.)

---

### 7.14 NHS Wales Lab Fee Management

**Role:** Dentist, Reception, Manager, Owner  
**Region:** Wales practices only

Manages laboratory fees for NHS Wales practices, applying tariff limits, HC3 exemption logic, and correctly splitting NHS-claimable versus private lab charges.

- Lab fee list with: patient, treatment, charge type (NHS/Private), lab amount, NHS tariff limit, actual charged, warranty flag, HC3 exemption applied, and invoice status
- **Add Lab Fee form** — patient, treatment, charge type toggle (NHS/Private), amount, and tariff limit; NHS lab fees are capped at the NHS tariff; HC3 exemptions automatically adjust the patient-payable amount
- KPI strip: NHS claimable total, Private lab total, Warranty labs excluded total, HC3 adjusted total
- **HC3 Logic tab** — explains and applies HC3 certificate logic (reduced patient contributions based on income/benefit status)
- **Tariff Validation tab** — validates submitted lab amounts against NHS Wales tariff caps; flags over-tariff amounts
- **Reporting tab** — lab fee breakdown by type and status
- Warranty-related lab work is automatically excluded from NHS claim calculations

---

### 7.15 NHS Wales Referral and Referral Care Package System

**Role:** Dentist, Reception, Manager, Owner  
**Region:** Wales practices only

Manages all referral types within NHS Wales — urgent (DAP), advanced services, high-needs, and outgoing referrals — generating the correct Care Package and tracking non-attendance.

- Referral plan list with type badge (Urgent/Advanced), submission status, and patient details
- KPI strip: urgent referrals, non-attended claims, advanced services, high-needs, submitted
- **New patient banner** — if the patient has no NHS claim in the previous 3 years, a banner flags they may qualify as New Patient Urgent Referral (DAP)
- Per-referral plan settings: referral type, new patient flag, urgent referral flag, non-attendance flag, DBOH (dietary advice, smoking, alcohol, fluoride) checkboxes, outgoing referral flags (High Needs, Advanced Services)
- **Non-Attended claims** — when a patient fails to attend a referral appointment, the non-attended flag generates the appropriate reduced-value claim
- **Referral Types tab** — reference list of all Wales referral types with descriptions and remuneration values
- Submit generates the appropriate Care Package (CPE for urgent referrals); claim status tracked from Draft → Submitted

---

### 7.16 NHS Wales Incomplete Work and Prep-Only Eligibility

**Role:** Dentist, Reception, Manager, Owner  
**Region:** Wales practices only

Real-time eligibility engine for NHS Wales Care Package claims where treatment is incomplete, determining whether each Care Package can be claimed based on current completion state.

- Package-level eligibility display: each Care Package in the treatment plan shows Claimable, Not Claimable, or Auto-Downgraded status with a one-line reason
- Tooth count indicator — shows the number of teeth with completed treatment; Extensive Restorative requires more than 4 teeth; if fewer are completed, the package is automatically downgraded to Simple Restorative
- **Prep-Only override** — treatments where only the preparation is complete (e.g. Crown Prep) are still claimable; the engine flags these as Prep-Only claims with the correct Care Package
- KPI strip: claimable packages, non-claimable (incomplete), auto-downgraded, prep-only claims
- Toggle individual treatment items as done/not done; eligibility recalculates instantly
- Each Care Package card shows patient charge and practice fee, and the reason for the eligibility decision

---

### 7.17 NHS Regional Rules and Claim Routing Engine

**Role:** Dentist, Reception, Manager, Owner

Routes NHS claims to the correct regional BSA gateway automatically by detecting the practice location's NHS region and applying the appropriate claim form, validation rules, and submission endpoint.

- **Claim Routing tab** — overview of the four NHS regions (England, Wales, Scotland, Northern Ireland) with claim form, currency, and submission endpoint for each; "Test Claim Routing" tool: select a patient and location, click Determine Routing, and the system shows the region, claim form, and all validation rules that will be applied
- **Location Config tab** — list of all practice locations with their assigned NHS region, contract, and active status
- **Rules Engine tab** — per-region list of active validation rules (e.g. England: UDA band auto-calculation, fissure sealant Band 2 from Apr 2026; Wales: Care Package auto-mapping, ethnicity mandatory; Scotland: capitation claim type, ASN marker; NI: panel number required, Tier Amount prior approval)
- **Rules Versioning tab** — changelog of NHS ruleset versions applied to each region

---

### 7.18 NHS Enterprise Hub

**Role:** Dentist, Manager, Owner  
**Plan:** Enterprise

A multi-contract NHS hub combining orthodontics, Scotland-specific workflows, document management, reconciliation, AI validation, referral management, compliance, patient comms, monitoring, and UDA/UOA forecasting in one consolidated interface.

- **Orthodontics tab** — FP17O/FP17PR claim management; IOTN scoring tool (DHC grades 1–5 and AC grades 1–10) with automatic eligibility determination; Part 1/Part 2 ortho claim lifecycle; NHS Ortho contract UOA tracking
- **Documents & Signatures tab** — manage FP17, FP17PR, and consent forms; signed/unsigned status; view and countersign documents inline
- **Scotland Workflow tab** — Scotland-specific claim management with HCN/CHI patient identifiers; capitation and restorative claim types; ASN (Additional Support Needs) marker with Section X Code 10(b)
- **Reconciliation tab** — period-by-period comparison of Compass UDA count vs claimed UDAs; highlights discrepancies, minor variances, and reconciled periods; payment total per period
- **AI Validation tab** — AI-driven risk scoring of pending claims; flags High/Medium/Low risk with specific issues and suggested corrections (e.g. expired Free Repair marker, missing ethnicity, missing Location ID)
- **Referral Management tab** — track CDS, Ortho, and Advanced referrals with priority and status; includes domiciliary care referrals
- **Compliance tab** — cross-region compliance status overview
- **Patient Comms tab** — NHS-specific patient communication templates and send log
- **Monitoring tab** — NHS API connectivity and submission pipeline status
- **Forecasting tab** — year-end UDA/UOA projection based on current pace

---

### 7.19 NHS Regional Architecture

**Role:** Manager, Owner  
**Plan:** Growth, Enterprise (multi-site practices)

Practice-level configuration for multi-location NHS setups, allowing each practice site to have its own NHS region, contracts, UDA targets, submission credentials, and practitioner assignments.

- **Locations tab** — list of all practice sites with region, ODS code, NHS authority, and active status; add new location with name, address, region, and ODS code; each location has its own NHS region which automatically determines the claim form and submission endpoint
- **Contract Management** — per location: add, view, and configure NHS contracts (GDS, PDS, Ortho); each contract carries contract number, type, UDA/UOA target, start/end date, submission method (Compass/WebEDI/etc.), and region ruleset version
- **Claim Resolver tool** — select a location and contract, enter a test date, and the resolver determines: claim form type, region label, blocked or routed status, and any blocking reason (e.g. contract expired or not yet started)
- **Add Contract modal** — contract name, number, UDA target, submission method, start/end dates, and NHS region; selecting the region shows the claim form and submission endpoint that will be used
- Region-aware ruleset versioning: each contract records the ruleset version at the time it was configured (e.g. `england@2026.04`)

---

### 7.2 UDA Tracker

**Role:** Dentist, Manager, Owner

NHS Unit of Dental Activity tracking for the contract year.

- Per-dentist UDA progress card showing: annual target, completed UDAs, remaining UDAs, and on-track / behind-target status
- Progress bar colour-coded: green (on track), amber (at risk), red (behind)
- "Need X UDA/month to hit target" calculation updated monthly
- Period toggle: Week / Month / Quarter / Year
- Monthly UDA activity breakdown table with target vs actual per month

---

## 8. Communication Modules

### 8.1 Team Chat

**Role:** Reception, Dentist, Hygienist, Manager, Owner

Internal instant messaging between staff members within the practice.

- Real-time chat threads
- Unread message badge on the sidebar nav item
- All messages are practice-isolated (not visible outside the practice)

---

### 8.2 WhatsApp Business Inbox

**Role:** Reception, Manager, Owner

Two-way WhatsApp messaging with patients via the WhatsApp Business API.

- Conversation list showing all patient WhatsApp threads with unread count and last message preview
- Full chat view with message history, showing message type (WhatsApp, SMS, recall, payment reminder)
- **Reply** — compose and send a WhatsApp or SMS message to the patient
- **Book or reschedule** appointment directly from the chat window via an inline calendar modal
- Conversations linked to patient records (shows next appointment, outstanding balance, patient ID)
- Message templates available for common outreach (recall, confirmation, payment reminder)

---

### 8.3 Reception AI

**Role:** Reception, Manager, Owner  
**Add-on feature — £79/month**

A 24/7 AI phone receptionist that answers calls, books appointments, and handles patient enquiries without changing the practice's existing phone number.

- **Live / Paused toggle** — managers can pause the AI and forward calls to a fallback number
- **Dashboard tab** — today's call volume, appointments booked by AI, calls transferred to human
- **Call Inbox tab** — full list of incoming calls with transcript, detected intent, and outcome
- **Missed Calls tab** — calls the AI could not handle, with patient details and callback flag
- **Callbacks tab** — patients who requested a callback, with one-click dial
- **Analytics tab** — call volume trends, intent breakdown, booking conversion rate
- **AI Settings tab:**
  - Voice selection (British Female, British Male, etc.)
  - Tone (Friendly / Professional / Formal)
  - Custom greeting message
  - After-hours message
  - Fallback phone number (human transfer)
  - Emergency out-of-hours routing number
- **Opening Hours tab** — set practice opening hours used by the AI for in-hours/out-of-hours routing
- **Booking Rules tab** — configure which appointment types the AI can and cannot book autonomously
- **Setup & Test tab** — initiate a test call to verify the AI is answering correctly
- **Usage & Billing tab** — minutes consumed, overage charges, SMS sent
- Detects 14 call intent types including: booking, cancellation, emergency, prescription query, complaint, and general enquiry

---

### 8.4 Inbox (Comms Hub)

**Role:** Reception, Manager, Owner

A unified communications inbox combining email and SMS threads.

- **Email tab** — two-pane email client showing inbox list and full message view; compose new email; reply to existing threads; mark as read
- **SMS tab** — SMS message threads with patients; compose and send new SMS
- Unread message badges on nav item
- Messages tagged by type: enquiry, query, recall, complaint, etc.
- Manager view shows all staff communications; reception sees their own queue

---

## 9. Growth Modules

### 9.1 Revenue Recovery

**Role:** Reception, Manager, Owner

Automated and assisted outreach to recover lost or at-risk revenue.

- **Overview tab** — total revenue at risk (£), recovered this month (£), items not yet contacted, and items rebooked
- **Treatment Plans tab** — patients with accepted treatment plans who have not yet booked their appointment; value at risk per patient
- **Overdue Recalls tab** — patients overdue for their recall appointment; months overdue and estimated value
- **Cancellations tab** — cancelled appointments with patient details and the value of the cancelled treatment
- **No-Shows (DNAs) tab** — patients who did not attend; DNA count history per patient
- **Missed Calls tab** — incoming calls that went unanswered; patient name, number, and missed call time
- **Per-row actions:**
  - Preview outreach message before sending
  - Send message (WhatsApp, SMS, or email, per patient preference)
  - Offer finance (opens Patient Finance send workflow)
  - Mark as contacted / rebooked / converted
- **Bulk selection** — select multiple rows and send messages in bulk
- Outreach modal lets staff review and edit the message before sending

---

### 9.2 Short Notice List

**Role:** Reception, Manager, Owner

A list of patients who have opted in to receive notifications about last-minute appointment slots.

- Patient list with: name, phone, preferred contact method (WhatsApp/SMS), appointment type preference, availability notes, and response/booking status
- **Contact individual** — one-click to contact via their preferred channel (WhatsApp, SMS, call, or email)
- **Contact selected** — select multiple patients and send a batch message
- **Contact all** — broadcast the short-notice slot to all patients on the list
- Response status shown per patient (Responded / Booked)

---

## 10. Lab & Finance Modules

### 10.1 Lab Manager

**Role:** Dentist, Reception, Manager, Owner

Tracks all dental laboratory cases sent out and monitors return status.

- Case list showing: patient, lab name, case type, shade, sent date, due date, and status
- Statuses: In Lab | Arrived | Overdue | Sent
- **Summary stats:** Overdue count, In Lab count, Arrived (fit-ready) count
- **Chase** — log a chase call for overdue cases with timestamp
- **Mark arrived** — update a case to "arrived" status
- **Mark complete** — remove a case from the active list once fit is completed
- **Case notes** — add or edit notes per case (e.g. shade confirmation, special instructions)
- **New Lab Case** — create a new outgoing lab case

---

### 10.2 Accounts

**Role:** Reception, Manager, Owner

Patient account balances and payment management.

- List of all patients with outstanding balances, showing: amount, overdue status, last payment date, line items, and contact details
- Summary figures: total outstanding, total overdue
- **Payment actions per patient:**
  - Send Stripe payment link (emailed to patient)
  - Initiate card reader payment with custom amount
  - Mark as paid manually
- **Send payment reminder** — sends an SMS reminder to the patient with their outstanding amount
- Filter by overdue status

---

### 10.3 Patient Finance

**Role:** Reception, Manager, Owner

Manages patient finance (credit) applications for high-cost treatments.

- **Applications tab** — list of all submitted finance applications with: patient, provider, treatment, amount, term, monthly repayment, status, and decision
- **Providers tab** — configure which finance providers are connected (e.g. Chrysalis Finance, DentiCare)
- **Send Finance Application** — complete a form (patient name, email, amount, provider, treatment) and send a secure application link to the patient; decision automatically attaches to the patient record when completed
- Application statuses: Pending | Approved | Declined
- Finance decisions and agreements stored against the patient record

---

### 10.4 Payments

**Role:** Manager, Owner

Payment provider configuration and transaction log.

- **Payment provider cards:** Stripe (card), Chrysalis Finance, GoCardless (direct debit), Square — showing connection status and fee structure
- **Connect a provider** — enter API key/secret to connect a new payment provider
- **Disconnect** a provider
- **Recent Transactions table** — shows patient name, amount, payment method, date, reference, and status (Paid/Pending)

---

### 10.5 Reports

**Role:** Manager, Owner

Practice-level analytics with bar, line, and pie charts plus tabular reports.

Available report types:
- **Monthly Revenue Summary** — total, NHS, and private revenue by month with month-on-month comparison
- **DNA & Cancellation Analysis** — DNAs and cancellations by day of week; revenue lost
- **UDA Performance Report** — UDA completed vs target per dentist per month
- **New Patient Report** — new patient volume by acquisition source (Google, referral, walk-in, social media); NHS vs Private split; conversion rate
- **Chair Utilisation** — utilisation percentage per surgery per week
- **Patient Retention** — recall return rate trend over 6 months; overdue and lapsed patient counts
- **Outstanding Balances** — list of patients with balances, days overdue, and status
- **FP17 Claims Summary** — claims by status, band breakdown, and submission rate

Each report can be exported or printed from within the report view.

---

## 11. My Space Modules

### 11.1 My Performance

**Role:** Dentist, Hygienist, Manager, Owner

Individual performance dashboard tailored to the logged-in user's role.

- **Reception view:** patients checked in, calls handled, appointments booked, DNAs followed up; daily activity table; outreach performance (WhatsApp open rates, SMS confirmations, recalls converted)
- **Dentist view:** patients seen, UDA completed (% of target), treatment revenue, notes finalised rate; treatment band breakdown with revenue; clinical performance metrics (avg treatment time, DNA rate, FP17 submission rate, same-day note completion)
- **Hygienist view:** hygiene sessions, recalls booked (and conversion rate), BPE average score, revenue generated; treatment mix breakdown
- **Manager view:** practice revenue MTD, team utilisation, DNA rate, AI-recovered revenue; staff performance table; AI feature impact (calls handled, recovery pipeline, recall bookings); operational wellbeing (AI hours saved, overloaded clinicians, inbox overload flags, practice health score)
- Period toggle: week / month

---

### 11.2 Daily Tasks

**Role:** Reception, Dentist, Hygienist, Manager, Owner

A personal task list for the logged-in user.

- Tasks grouped by due date: Today | This Week
- Task priority: Urgent | Normal | Low — colour-coded with a left-border indicator
- Task category labels (NHS, Appointments, Lab, Patients, Practice, General)
- **Add task** — type a task name and press Enter or click Add
- **Complete task** — tick the circle to mark done; completed tasks shown at the bottom with strikethrough
- Summary stat tiles: Urgent pending, Total pending, Completed today

---

### 11.3 Staff Rota

**Role:** Reception, Dentist, Hygienist, Manager, Owner

Weekly staff rota and holiday management.

- **Rota tab** — week-by-week grid showing each staff member's working pattern (Working, Annual Leave, Sick, Training, Bank Holiday)
- Week navigation: browse forward/backward through weeks
- **Manager actions:**
  - Edit any staff member's rota cell by selecting a shift type
  - Customise per-staff colour coding
  - Toggle rota visibility per staff member
  - **Publish rota** — locks the rota and notifies staff
- **Holidays tab:**
  - View all holiday requests with status (Pending / Approved / Declined)
  - Holiday allowance balance per staff member (days remaining from the 25-day annual allowance)
  - **Submit holiday request** (all staff) — enter from/to dates and reason; submitted as pending for manager approval
  - **Approve or decline** holiday requests (manager only); approved days are automatically deducted from the staff member's balance
- **Settings tab** — configure annual leave allowances and rota defaults

---

## 12. Practice Administration Modules

### 12.1 Practice Portal (Manager Portal)

**Role:** Manager, Owner

The central management dashboard for the practice.

- **Practice Health Gauge** — overall practice health score with breakdown by category
- **Operational Intelligence** — AI-surfaced issues (e.g. overloaded clinicians, diary pressure, recall backlog)
- **Pending approvals** — staff requests for changes to protected settings (Practice Name, CQC, GDC) that require manager sign-off
- **Super Admin access requests** — view any active ProDentalConnect support access sessions granted to this practice
- **Deletion request management** — review and approve/decline patient data deletion requests raised by staff
- Treatment plan management (manager-level view of all treatment plans across the practice)

---

### 12.2 Users

**Role:** Manager, Owner

Add and manage staff accounts.

- **Staff list** with role, status (active/inactive), last login, and seat usage vs plan limit
- **Seat usage indicator** — progress bar showing active seats vs plan allowance; warning at 80% capacity
- **Add staff member** — form to enter name, email, and role (Reception, Dentist, Hygienist, Manager); an email invite is sent automatically
- **Deactivate / reactivate** a user account
- **Change role** — role change resets permissions to the new role's defaults
- **Per-user permission override** — toggle individual permissions on or off for each user, overriding role defaults
- **SSO card** — view and manage the SSO (Google/Microsoft) account linked to a user

---

### 12.3 Features & Plans (Subscription)

**Role:** Manager, Owner

Browse and manage the features available on the practice's current plan.

- **Active feature cards** — features included in the current plan, with usage indicators
- **Locked feature cards** — features available on higher plans, with an "upgrade" prompt
- **Feature detail modal** — full description, plan availability, and upgrade path for any feature
- Current plan and billing information shown at the top

---

### 12.4 Templates

**Role:** Manager, Owner

Manage message and document templates used across the platform.

- **Template library** — browse by category (e.g. Recall, Appointment, Payment, Clinical, Consent)
- Search templates by name
- **Template detail panel** — preview the full template text with placeholder variables highlighted (e.g. `[Patient Name]`, `[Date]`, `[Treatment]`, `[Cost]`)
- **Edit template** — inline editor with monospace text area; save changes back to the library
- **Copy template** — copy to clipboard for use in external messaging
- **Use Template** — inserts the template into the relevant messaging workflow
- **Create new template** — create a blank template from scratch

---

### 12.5 Audit Log

**Role:** Manager, Owner

An immutable system-wide log of all actions taken within the practice.

- Timestamped entries recording: user, action type, target (patient ID or record type), field changed, old value, new value
- Exported to meet CQC and ICO record-keeping requirements (7-year retention)
- Filter by user, date range, and action type

---

### 12.6 Settings

**Role:** Manager, Owner

Comprehensive practice configuration, organised into sections:

- **Practice Details** — practice name, CQC registration, GDC number, address, phone, email, ODS code, Performer PIN. Changes to CQC, GDC, and ODS require Super Admin approval.
- **Staff & Users** — shortcut to Users page
- **Calendar & Appointments** — default appointment duration, working hours start/end, DNA threshold (auto-flag after N DNAs), appointment reminder timing, cancellation buffer
- **Clinical Settings** — clinical workflow preferences
- **Medical History Questions** — add, edit, enable, or disable questions in the medical history questionnaire used on all patient records; questions can have conditional follow-up fields
- **Treatment Settings** — map treatment codes to SNOMED CT codes; search by treatment name, treatment code, or SNOMED code
- **Dashboard Visibility** — configure which KPI widgets are visible on the dashboard
- **NHS Configuration** — NHS contract number, UDA annual target, BSA submission method, recall interval, band charge amounts (Band 1/2/3)
- **Backup & Data** — backup frequency (hourly recommended), retention period (90-day rolling default)
- **Integrations** — third-party integration configuration (links to the Integrations page)
- **Notifications** — configure notification channels per event type (patient reminders, staff rota published, FP17 rejections, DNA alerts, revenue recovery digest, system maintenance)
- **Billing & Payments** — current plan, next billing date, payment method, invoice email, auto-renewal
- **Security** — two-factor authentication (mandatory for managers), session timeout, password policy, IP allowlist, audit log retention
- **Branding** — practice name on communications, SMS sender name, email from name, primary colour, logo upload (drag-and-drop)
- **Super Admin Access** — grant ProDentalConnect support access for 1 hour, 4 hours, or 24 hours; all access sessions are logged and audited (Article 28 compliant)

---

### 12.7 Business Copilot

**Role:** Manager, Owner  
**Add-on feature — £49/month**

An AI-powered business advisor embedded in the platform as a slide-out chat panel. Business Copilot has access to the practice's real operational data — revenue, team performance, appointment trends, and patient metrics — and answers questions from owners and managers with data-driven analysis.

- **Chat interface** — free-text question input; the AI responds with bullet-point analysis, specific figures (with £ signs), and actionable recommendations; responses are formatted with bold section headers and bullet points for clarity
- Questions answered include: revenue trends, which dentist is underperforming, recall conversion, DNA patterns, outstanding balances, UDA progress, and cost reduction opportunities
- Greeting message on first open references the actual practice name and today's date
- **Subscription wall** — unsubscribed practices see a teaser response and are prompted to subscribe; subscribed practices receive full AI analysis backed by live practice data
- Subscribe / activate flow built into the panel header (£49/month add-on)
- Panel can be opened from anywhere in the app; closes without losing conversation history during the session

---

### 12.8 Integrations and Connected Software

**Role:** Manager, Owner

A directory of third-party integrations available to connect to the practice's ProDentalConnect account.

- Integrations grid showing all available connectors grouped by category (e.g. Imaging, Finance, Communication, Lab, Clinical)
- **Status badge per integration** — Connected or Available
- **Category filter tabs** — filter the grid by integration category; "All" shows the full list
- **Search** — live text search by integration name or description
- **Active integrations counter** — "X of Y integrations active" shown in the header
- **Configure modal** — click any integration to open a configuration panel with API key / credential entry; save connects the integration and updates its status badge
- **Disconnect** — remove an existing connection from the configure modal
- **Request Integration modal** — submit a request for a new integration not yet in the catalogue: name, website URL, and use-case description; submitted to the ProDentalConnect team for review
- Toast confirmation on successful connection or disconnection

---

### 12.9 HR Leave Management

**Role:** Reception, Dentist, Hygienist, Manager, Owner

A dedicated HR leave management module for tracking staff leave requests, allowances, and approvals.

- **Overview tab** — summary of all staff with their leave allowances and used days per leave type
- **Staff leave cards** — per staff member: annual leave used vs allowance, sick days, compassionate leave, training days, and other leave types
- **Pending approvals** — manager view shows all pending leave requests across the team with staff name, role, leave type, dates, day count, and reason; approve or reject with one click; approved leave automatically updates the staff rota and deducts from the allowance balance
- **New Leave Request modal** — all staff can submit requests; managers can submit on behalf of any team member; leave type selector (Annual Leave, Sick, Compassionate, Training, Other); from/to date picker with automatic day count calculation; notes field
- **Leave conflict detection** — checks for existing approved leave on the requested dates for the same staff member
- **Set Allowances modal** — managers can configure annual allowance per leave type per staff member
- Staff rota is updated automatically when leave is approved

---

### 12.10 Appointment Audit Page

**Role:** Manager, Owner

An immutable audit trail specifically for appointment-level changes: cancellations, DNAs, reschedules, and creation events.

- **Two views:** Timeline (chronological event feed) and Table (sortable grid)
- **Filters:** action type (cancelled, DNA, moved, created), dentist/provider, date (today, yesterday, all), and free-text search by patient name, reason, or treatment type
- **Summary KPI tiles** — total audit entries, cancellations, DNAs, and moves at a glance
- Each audit entry records: timestamp, patient name, action type (with colour-coded icon), from appointment (time, provider, treatment type), to appointment (for moves), reason, actioned by, and role
- Click any entry to open a **Detail Panel** with full breakdown of the appointment change, before/after comparison, and the reason logged
- **Export to CSV** — exports the current filtered view with all fields to a dated CSV file
- Separate from the general Audit Log (Section 12.5); focused exclusively on appointment-level changes

---

## 13. Help & Support

**Role:** All roles

In-app support ticket system.

- **Ticket list** — view all open and resolved tickets for the practice, filterable by status
- **New ticket** — form to submit a support request with title, category, priority (Low/Medium/High/Critical), and description
- **Ticket detail** — view full ticket conversation and add replies; messages are exchanged between practice staff and the ProDentalConnect support team
- **Contact channels displayed** based on the practice plan: Starter (portal only), Growth (portal + email), Scale (portal + email + phone + Slack)
- Response time SLA shown based on the practice plan

---

## 14. Patient Portal

The Patient Portal is a separate mobile-optimised web page accessed by patients. It does not require them to install an app.

### 14.1 Home (Dashboard)

- **Personalised greeting** with the patient's name and next appointment date/time/dentist
- **Pre-visit checklist** — shows items the patient needs to action before their upcoming appointment (confirm appointment, update medical history, pay outstanding balance, review prep tips)
- **Quick action buttons** — Book appointment, Pay balance, Update medical history, View messages
- **Next appointment card** — date, time, clinician, treatment, and duration with self-check-in button
- **Recent activity feed** — appointment confirmations, treatment plan updates, completed treatments, recall reminders
- **AI dental assistant prompt** — quick-access button to the AI chat

### 14.2 Appointments

- **Upcoming appointments** — full details per appointment (date, time, treatment, clinician, location, duration, confirmation status)
- **Past visits** — history of completed appointments with treatment type and clinician
- Actions per upcoming appointment: self check-in, view details, request reschedule, cancel

### 14.3 AI Dental Assistant

A conversational AI chatbot that answers patient questions about their dental care.

- Patients can ask about their next appointment, outstanding balance, how to pay, preparation tips, what a treatment involves, after-care instructions, and more
- **Quick reply chips** — suggested follow-up questions displayed after each AI response
- The AI uses the patient's actual appointment, balance, and medical context to give personalised responses
- Supports check-in confirmation, treatment plan queries, cost queries, NHS band queries, and post-op care guidance

### 14.4 My Care

Organised into three sub-sections:

- **Plans** — view the current treatment plan with line items, NHS band, and total cost; accept or decline the treatment plan; finance options (Chrysalis 0% finance, payment plan) shown inline
- **Forms** — view and update the medical history questionnaire; view signed consent forms; sign pending consent forms (e-signature in browser)
- **Documents** — download treatment reports, invoices, aftercare leaflets, and signed consent forms

### 14.5 Self Check-In

A dedicated check-in screen accessible from the appointment card.

- Patient confirms they have arrived; the practice is notified automatically
- Estimated wait time displayed
- While waiting, the patient is prompted to review their treatment plan or update their medical history

### 14.6 Book Appointment

A 3-step booking request flow:

1. **Step 1 — Select type:** Choose appointment type (Routine Check-up, Emergency, Scale & Polish, New Patient Examination, Whitening Consultation), preferred clinician, and add notes
2. **Step 2 — Choose date/time:** Pick from available dates and time slots
3. **Step 3 — Review & confirm:** Summary of the booking; submit sends a request to the practice for confirmation; patient receives an SMS within 2 hours

### 14.7 Medical History (Patient-side)

Patient-facing version of the medical history questionnaire.

- Current medications field (pre-populated from record)
- Medical condition toggles (same conditions as the practice-side record)
- Allergy information
- Submission sends the updated history to the practice; a confirmation message confirms the clinician will review before the appointment

### 14.8 Payments

- View outstanding balance with overdue flag and line items (e.g. Band 2 NHS treatment)
- **Pay now** — opens a secure Stripe payment page
- **Instalment plan** — request a payment plan (connects to reception)
- View payment history

### 14.9 Profile

- View personal details: name, date of birth, NHS number, phone, email, address
- Communication preferences: preferred contact method, appointment reminder channels (SMS/email), recall reminder settings
- View assigned dentist and practice contact details
- Sign out

---

## 15. Roles & Permissions Summary

### Default Role Access by Module

| Module | Reception | Dentist | Hygienist | Manager | Owner |
|---|:---:|:---:|:---:|:---:|:---:|
| Dashboard | Yes | Yes | Yes | Yes | Yes |
| Daily Priorities | Yes | Yes | Yes | Yes | Yes |
| Morning Huddle | Yes | No | No | Yes | Yes |
| Calendar | Yes | Yes | Yes | Yes | Yes |
| Waiting Room | Yes | Yes | Yes | Yes | Yes |
| Patients | Yes | Yes | Yes | Yes | Yes |
| Online Booking | Yes | No | No | Yes | Yes |
| Clinical Notes | No | Yes | Yes | Yes | Yes |
| X-Ray Imaging | No | Yes | No | Yes | Yes |
| FP17 Claims | Yes | Yes | No | Yes | Yes |
| UDA Tracker | No | Yes | No | Yes | Yes |
| Team Chat | Yes | Yes | Yes | Yes | Yes |
| WhatsApp | Yes | No | No | Yes | Yes |
| Reception AI | Yes | No | No | Yes | Yes |
| Inbox | Yes | No | No | Yes | Yes |
| Revenue Recovery | Yes | No | No | Yes | Yes |
| Short Notice | Yes | No | No | Yes | Yes |
| Lab Manager | Yes | Yes | No | Yes | Yes |
| Accounts | Yes | No | No | Yes | Yes |
| Patient Finance | Yes | No | No | Yes | Yes |
| Payments | No | No | No | Yes | Yes |
| Reports | No | No | No | Yes | Yes |
| My Performance | No | Yes | Yes | Yes | Yes |
| Daily Tasks | Yes | Yes | Yes | Yes | Yes |
| Staff Rota | Yes | Yes | Yes | Yes | Yes |
| Practice Portal | No | No | No | Yes | Yes |
| Users | No | No | No | Yes | Yes |
| Features & Plans | No | No | No | Yes | Yes |
| Templates | No | No | No | Yes | Yes |
| Audit Log | No | No | No | Yes | Yes |
| Settings | No | No | No | Yes | Yes |
| Help & Support | Yes | Yes | Yes | Yes | Yes |

### Permission Overrides

Managers can override individual permissions per staff member from the Users page, granting or restricting access to specific modules beyond the role defaults. Changes are applied immediately and logged in the Audit Log.

### Super Admin

The Super Admin role is reserved for ProDentalConnect platform administrators. Super Admins see a separate admin sidebar with tools for managing all practices, subscriptions, platform AI, system monitoring, security, cloud backup, support tickets, software updates, and announcements. Super Admin login always requires 2FA. Full detail on each admin tool is in Section 16.

---

*For technical support, use the Help & Support page within the app or email support@prodental.co.uk*

---

## 16. Super Admin Tools

The Super Admin interface is a separate admin console accessible only to ProDentalConnect platform staff. All Super Admin sessions require 2FA login. Every action in the admin console is logged to the immutable platform audit trail.

---

### 16.1 Admin Dashboard

**Role:** Super Admin

The platform-wide overview screen showing headline operational metrics for the entire ProDentalConnect platform.

- **Hero KPI tiles (4):** Monthly Recurring Revenue (MRR) across all active practices, Active Practice count (with trial count sub-label), Total Patient Records across all practices, and System Uptime (%)
- **Practice Overview panel** — list of practices with location, user count, patient count, plan badge (Starter/Growth/Enterprise), status indicator (active/trial/suspended), and MRR per practice
- **System Status panel** — real-time status of all platform services: API Gateway, Database Cluster, PDF Generation, Email (SendGrid), SMS (Twilio), WhatsApp API, NHS BSA API; services show Operational or Degraded with latency/reason on hover
- **Plan Distribution panel** — bar chart showing how many practices are on each plan (Enterprise, Growth, Starter)
- **Recent System Activity feed** — timestamped platform events: new trials, plan upgrades, payment failures, deployment completions, API rate limit warnings, and new feature activations

---

### 16.2 Admin Pricing (Plan Builder)

**Role:** Super Admin

Full control over ProDentalConnect subscription plans and add-on pricing.

- **Plans view** — list of all subscription plans (Core, Starter, Growth, Enterprise, Multi-Clinic) with price, practice count, "most popular" badge, highlighted status, and MRR contribution; click any plan to edit
- **Plan Editor** — edit plan name, monthly price, badge text, feature flags (on/off per feature category: Core, NHS, Clinical, Comms, Growth, Reports, AI, API, Support), and per-plan limits (patient records cap, dentist seats, staff seats, SMS monthly allowance, extra SMS rate, email allowance, AI phone minutes, storage GB, support tier, SLA percentage, onboarding type, contract length)
- **Create New Plan** — blank plan template with all configurable fields
- **Delete Plan** — confirm before removing a plan; active practices on the plan are flagged
- **Add-ons view** — list of all add-on products (Reception AI, WhatsApp Business, Business Copilot, Lab Portal Pro, X-Ray Cloud Sync, Patient Finance) with monthly price, description, and active/inactive toggle; edit any add-on's price inline
- **Plan Builder tab** — visual feature-by-feature comparison matrix across all plans; tick/untick features per plan; shows which plan each feature is first available on
- **MRR calculator** — live total MRR across plans and add-ons updates as prices are changed

---

### 16.3 Admin Treatment Plans (Platform Pricing)

**Role:** Super Admin

Manage the default treatment plan price list used as the platform baseline across all practices.

- Full price list table: treatment code, description, category (NHS, Private, Implant, Orthodontics, etc.), and NHS/Private fee
- **Category filter tabs** — filter the list by treatment category
- **Search** — live filter by treatment code or description
- **Inline price editing** — click any fee to edit it; edited rows are highlighted until saved
- **Bulk Price Adjustment modal** — increase or decrease all prices (or a selected category) by a percentage in one action; select increase/decrease direction and percentage; preview of new prices
- **Push to All Practices** — deploy the updated price list to all 127+ practices platform-wide with one click
- **Reset to Defaults** — revert all prices to platform defaults; confirmation required
- Changed rows are tracked and highlighted until pushed or reset

---

### 16.4 Admin Monitoring (Infrastructure & Services)

**Role:** Super Admin

Comprehensive real-time infrastructure monitoring across all ProDentalConnect platform services.

- **Overview tab** — service health cards for all platform services (API Gateway, PostgreSQL, Redis, AI Engine, Twilio, S3, SendGrid, WhatsApp API) with: uptime %, average latency, P95 and P99 latency, status (healthy/degraded/down), region, and last incident date; colour-coded overall platform status banner
- **Latency Charts tab** — 24-hour time-series charts for API, Database, and AI Engine latency (line charts, hourly resolution)
- **Error Rate tab** — 24-hour time-series for HTTP 4xx and 5xx error rates
- **Traffic tab** — requests per minute over 24 hours
- **Infrastructure tab** — server-level metrics per host (app servers, DB primary and replica, Redis, worker): CPU %, memory %, disk %, network throughput, status (healthy/warning)
- **AI Usage tab** — per-model AI usage: calls, token count, cost (£), average latency, and error count for all models (GPT-4o clinical summaries, GPT-4o-mini Reception AI, GPT-4o-mini Business Copilot, Whisper transcription); total AI cost MTD
- **Incidents tab** — list of current and historical incidents with: ID, title, severity, start time, resolution time, impact description, and duration; active incidents shown with "ongoing" badge
- **Alerts** — configure alert thresholds per service; PagerDuty integration shown

---

### 16.5 Admin Platform AI

**Role:** Super Admin

An AI-powered platform management assistant that allows Super Admins to make changes to the ProDentalConnect app using natural language — either as live in-app changes or as generated source-code updates.

- **Chat tab** — conversational interface for requesting app changes; the AI can make "live changes" (toggling features, navigation changes, colours, patient data) instantly, or "code changes" (new pages, bug fixes, layout changes) by generating updated source code for download
- **Smart Component Extractor** — when the source code is loaded, the AI automatically identifies the relevant React component for the requested change using a keyword-to-component mapping, extracts only that section, and sends it to the AI to minimise token usage
- **Setup tab** — paste in the full App.jsx source code; once loaded, the AI uses it as context for all subsequent code-change requests; source is persisted in local storage across sessions
- Download updated file — code changes are delivered as a downloadable `.jsx` file
- AI self-identifies as "Platform AI" and never mentions Claude or the underlying model

---

### 16.6 Admin Updates (Software Deployment)

**Role:** Super Admin

Manages software version control and deployment of updates to all practices on the platform.

- **Deploy tab:**
  - Bump type selector: Patch, Minor, Major, or Hotfix; live preview of next version number
  - Custom version input (override auto-bump)
  - Changelog text field — written description of changes included in the deployment
  - Deploy target: All Practices, or a single named practice
  - Upload new build: drag-and-drop or file-select `.jsx` or `.zip` source file; file name and size shown on upload
  - "Deploy to [X] Practices" button with live progress bar and deployment log (timestamped step-by-step output)
  - Deployment result: success confirmation with new version number and practice count
- **Version History tab** — list of all past deployments with: version number, date, type (feature/bugfix), changelog summary, practice count pushed to, deployed by, and status (current/deployed/deprecated)
- **Feature Flags tab** — toggle individual features on or off platform-wide (Reception AI, WhatsApp Messaging, Short Notice Filler, Revenue Recovery, X-Ray Imaging, Lab Manager, Practice Reports, Patient Finance, Calendar, Patient Records, and others); core features are locked and cannot be disabled
- Version state is shared with the platform version indicator shown to all users

---

### 16.7 Announcements Admin

**Role:** Super Admin

Platform-wide announcement management: create, schedule, target, and monitor the delivery of announcements to practices and staff users across the platform.

- **Announcement list tab** — all announcements with status (Draft / Active / Paused / Expired), type, priority, and delivery stats; filter by status and type; send now, pause, edit, or delete each announcement
- **Announcement Builder modal:**
  - Title and message body (supports line breaks)
  - Type (General, Feature Update, Maintenance, Billing, Security, etc.)
  - Priority (Low / Normal / High / Critical)
  - Display Mode (Banner, Modal, Blocking, Bell notification)
  - Target Audience: All Practices & Users, Selected Practices, Individual Practice, Selected Roles, Trial Only, Overdue Billing, Beta Practices
  - Scheduling: start date, expiry date, recurrence rule (once, daily, weekly)
  - Acknowledgement requirement: require explicit user acknowledgement before dismissal
  - Snooze settings: allow snooze, snooze duration (hours), allow "don't show again"
  - Blocking mode: prevents app use until acknowledged
  - Action button: optional label and URL
  - Release version tag
- **Preview** — live preview of the announcement in the selected display mode (banner, modal, blocking overlay, or bell notification) before sending
- **Delivery stats** — per announcement: targeted users, viewed count, acknowledged count, and acknowledgement rate
- **Audit tab** — log of which practices and users have viewed and acknowledged each announcement, filterable by announcement, practice, and acknowledgement status

---

### 16.8 Appointment Audit (Platform-wide)

**Role:** Super Admin

*This is the same Appointment Audit page as Section 12.10, surfaced in the Super Admin console with the ability to view audit entries across all practices (not just one).*

- All features of the practice-level Appointment Audit (see Section 12.10)
- Additional practice selector — filter by All Practices or a specific practice
- Exports cover the full cross-practice dataset

---

### 16.9 Admin Security

**Role:** Super Admin

Platform-level security monitoring, compliance tracking, active session management, and SSO configuration.

- **Overview tab** — security status summary: login success/failure counts, high-risk events flagged, active sessions, and compliance score; key security indicators (MFA coverage, policy compliance, recent failed logins)
- **Audit Log tab** — platform-wide security event log with: user, action type (login, edit, view, delete, failed login, export, settings change), target resource, IP address, timestamp, and risk level (Low/Medium/High); colour-coded by event type; filterable
- **Infrastructure tab** — list of all platform infrastructure components (Production DB, Application Server, File Storage, CDN, Backup Store, Email Gateway) with: provider, region, status, encryption standard, backup schedule, and uptime
- **Compliance tab** — staged compliance roadmap showing: Foundational (Cyber Essentials, GDPR, MFA, Automated Backups, Security Policies, RBAC — all complete), Advanced, and Enterprise compliance stages with individual item status and detail
- **Active Sessions tab** — real-time list of all active admin sessions: user, device/browser, IP address, location, session start time, last activity, and MFA status; "Terminate Session" action per non-current session
- **SSO Management tab** — configure and manage SSO providers (Google, Microsoft); view which admin users have SSO linked; manage SSO client credentials

---

### 16.10 Admin Users (Platform Staff)

**Role:** Super Admin

Manage the ProDentalConnect internal admin team — the staff who have access to the Super Admin console.

- Admin team list showing: name, email, role (Super Admin, Support Agent, Developer, Customer Success), last login, status (active/inactive), avatar, and per-module permissions
- **Invite Admin User** — form to add a new admin team member: name, email, and role
- **Permissions modal** per user — toggle granular access on/off for each admin module: All Practices, Billing & Plans, Admin Users, Feature Control, System Monitoring, Support Tickets, Deployments
- **Revoke Access** — immediately deactivates the user and strips all permissions; action is logged; confirmation modal required
- **Role labels** — Super Admin, Support Agent, Developer, Customer Success (used to describe the team member's function, separate from permissions)
- Permission changes take effect immediately and are logged to the platform audit trail

---

### 16.11 Admin Support Access (GDPR-compliant)

**Role:** Super Admin

Manages time-limited support access sessions where ProDentalConnect support agents need to access a practice's data to diagnose issues. All access is logged and GDPR Article 28 compliant.

- List of active and historical support access requests with: requesting agent, target practice, reason, request time, approved duration, and status (Pending Approval / Active / Expired)
- **Approve** or **Deny** pending requests; approved sessions are activated immediately and the practice is notified by email
- **Revoke** an active support session at any time
- **View Log** — opens a detailed access audit log for each session showing every action the agent performed, with timestamps and log levels (info/warn/success/error)
- Export log to file
- Access auto-expires after the approved duration (1 hour, 4 hours, or 24 hours)
- Info banner: "All support access is logged to the immutable audit log. Access auto-expires after the approved duration." GDPR Article 28 compliance note displayed

---

### 16.12 Admin Tickets (Support Ticket Management)

**Role:** Super Admin

Full support ticket management interface for the ProDentalConnect support team.

- **Two-pane layout** — left panel: ticket list with search and filters; right panel: full ticket conversation thread
- **Ticket list filters** — by status (Open / In Progress / Resolved / Closed), priority (Low / Medium / High / Critical), and practice plan (Starter / Growth / Enterprise)
- Tickets sorted by priority (Critical first); each ticket row shows: ticket ID, priority badge, status badge, title, practice name, plan badge, channel icon (portal/email/phone/chat), and assignee
- **Summary KPI strip** — Open, Active (In Progress), Critical, and Resolved ticket counts
- **Ticket detail panel** — full conversation thread with timestamps; ticket metadata (practice, plan, channel, created date, last updated, assignee); status and assignee update controls; reply box
- Send reply — reply is added to the conversation and ticket status changes from Open → In Progress automatically; practice is notified
- Update status — manually set status to any stage
- Assign ticket — assign to a named support agent

---

### 16.13 Admin Support Config (Support Channel Configuration)

**Role:** Super Admin

Configures which support contact channels and SLA response times are available to practices on each subscription plan — these settings automatically populate what practices see in their Help & Support page.

- Three-column layout, one column per plan (Starter, Growth, Enterprise)
- Per plan configuration:
  - **Response Time SLA** — editable text field (e.g. "4 hours")
  - **Contact Channel toggles** — Email Support, Phone Support, WhatsApp Support, Live Chat, Dedicated CSM (on/off per plan)
  - **Phone number** — shown when phone is enabled
  - **WhatsApp number** — shown when WhatsApp is enabled
  - **CSM name and email** — shown when dedicated CSM is enabled
  - **Emergency/Out-of-hours line toggle** — separate emergency number field
  - **Support page display text** — the SLA description shown to practices on their Help & Support page; editable rich-text label
- "Save [Plan] Config" button per column; toast confirmation on save
- Changes take effect immediately on practices' Help & Support pages

---

### 16.14 Admin Reception AI (System Control)

**Role:** Super Admin

Platform-level control panel for the Reception AI add-on feature — enabling/disabling per practice, pricing management, provider configuration, and usage analytics.

- **Hero header** — shows globally enabled/disabled status, total add-on revenue (£/month), and number of active vs total practices
- **Global Feature Switch** — a single master toggle to enable or disable Reception AI for the entire platform; when off, no practice can activate it
- **Telephony Provider selector** — choose the active provider: Twilio (live), Vonage, Aircall, or SIP (planned); provider setting applies platform-wide
- **Pricing panel** — inline editable fields for: monthly base fee (£), included minutes, and extra per-minute rate (£); changes update billing automatically on next cycle
- **Platform Stats panel** — active practices count, total AI minutes consumed per month, total appointments booked by AI, and monthly revenue
- **Per-Practice Control table** — for each practice: name, plan, AI phone number (auto-provisioned on activation), enabled status, AI minutes consumed, calls handled, appointments booked, monthly bill impact, and an enable/disable toggle; disabling removes the AI number and stops billing

---

### 16.15 Admin Features (Feature Control)

**Role:** Super Admin

Granular per-practice and per-feature control over which add-on features are enabled across the platform.

- **Feature cards** — each add-on (Reception AI, WhatsApp Business, Business Copilot, Lab Portal Pro, X-Ray Cloud Sync, Patient Finance) shown with icon, name, price per practice, and count of enabled vs total practices; total add-on revenue calculated live
- **Manage Per-Practice modal** — for a selected feature: list of all practices with an enable/disable toggle per practice; shows enabled count and total monthly add-on revenue; save applies changes
- **Practice Settings modal** — configure a feature's settings for a single practice or bulk-select multiple practices; scope selector (Single Practice / Bulk Select)
- **Add Feature modal** — define a new platform add-on: name, monthly price, provider, description
- Add-on revenue total across all features shown in the page header

---

### 16.16 Admin Practices

**Role:** Super Admin

Complete management of all dental practices on the ProDentalConnect platform.

- **Practice list** — searchable table of all practices with: name, location, plan badge, user count vs seat limit, patient count, UDA target, MRR, active add-ons, and status (active/suspended)
- **Total MRR** shown at the top of the list
- **Practice Detail view** — drill into any practice to see: plan, MRR, users/seats, patients, UDA target, add-on count; and perform actions: Reset Password, Resend Invite, Change Plan, Suspend Practice, View Reports
- Active add-ons displayed per practice; Integrations & Configuration panel embedded in the detail view
- **Add New Practice modal** — enter practice name, location, UDA target, plan (Starter/Growth/Enterprise), and seat limit; on creation, an onboarding email is sent automatically; practice is immediately active
- Status badge (ACTIVE / SUSPENDED) on each practice

---

### 16.17 Admin Data Manager

**Role:** Super Admin

Platform-level data operations for individual practices or all practices — covering GDPR exports, data imports, archiving, integrity checks, backups, and record purges.

- **Practice scope selector** — apply operations to All Practices or a specific named practice
- **Operation cards (6):**
  - **GDPR Data Export** — exports all patient data in JSON/CSV format; UK GDPR Article 20 compliant; download link sent to admin email
  - **Data Import / Migration** — three-step wizard: (1) choose source system (R4+, Dentally, EXACT, SOE Exact, Generic CSV) and upload file (.csv, .xml, .json, .zip up to 500MB); (2) preview detected records with validity indicator; (3) run import with live progress bar
  - **Archive Practice** — archive a suspended practice; data retained for 7 years per CQC; only available for suspended practices; destructive — confirmation required
  - **Data Integrity Check** — scans all records for orphaned data, missing NHS numbers, duplicate patients, and broken relationships
  - **Database Backup** — triggers an immediate AES-256 encrypted backup to AWS S3; supplements the existing automated backup schedule
  - **Purge Deleted Records** — permanently deletes records past their retention period; irreversible; explicit confirmation required
- Destructive operations require a two-step confirmation before execution
- Progress bars and success toasts for all operations

---

### 16.18 Admin System Monitoring

**Role:** Super Admin

Simplified real-time infrastructure health monitoring focused on external service connectivity and API performance.

- **Health tab** — status cards for all connected services: API Gateway, Database, NHS BSA Compass, WebEDI Wales, WhatsApp API, Twilio AI Phone, AWS S3 Backup, Email/SMTP, System Uptime; each card shows status (Online/Healthy/Degraded/Connected/Active/Synced) with latency or last-sync sub-label and a colour-coded left border
- **API tab** — top-5 API endpoints by call volume: endpoint path, calls per day, P95 latency, and error rate (colour-coded green/amber/red)
- **Errors tab** — "No issues in the last 24 hours" if clean; otherwise lists recent error events
- **Performance tab** — same as Errors tab; shows clean-bill or performance anomalies
- Tabs selected by underline navigation bar at the top of the page

---

### 16.19 Admin Cloud Backup

**Role:** Super Admin

Detailed cloud backup monitoring and management for all practice data across the platform.

- **Summary KPI strip** — healthy backups, warnings, critical/offline, and total storage (MB) across all practices
- **Per-practice backup job list** — each row shows: practice name, location, last backup timestamp, backup age, size, status (healthy/warning/critical/offline), last error, and retry count; actions per row: View Logs, View History, Retry, Manual Backup, View Details
- **Status indicators** — healthy (green), warning (amber — e.g. replication lag), critical (red — backup failed after 3 retries), offline (grey — backup agent not responding)
- **Backup Logs modal** — full step-by-step timestamped job log for the most recent backup run; metadata header (status, duration, file count, size, encryption method, replication status, compression, initiated by); failure analysis section explains the root cause when status is critical; Export log; Retry Backup button for failed jobs
- **Backup History modal** — rolling history of past backup runs per practice with status, size, duration, and file count per run; highlights failed runs; SLA compliance indicator
- **Details modal** — full technical configuration per practice: destination S3 path, encryption key, compression, retention period, replication status
- **Alert configuration** — toggle alert channels: email, in-app, SMS, Slack
- **Audit panel** — timestamped log of all manual backup actions taken by Super Admins

---

### 16.20 Admin Activity Log

**Role:** Super Admin

A cross-platform activity and appointment audit log covering all practices.

- **Two tabs:**
  - **Activity Log tab** — timestamped feed of all significant events across all practices: user, role, action, detail, practice, and action type (create/edit/delete/status change); filters: practice selector, action type; Export CSV button
  - **Appointment Audit tab** — cross-practice appointment audit (same as Section 12.10 but platform-wide); practice selector to drill into a specific practice; columns: timestamp, practice, patient/detail, actioned by, role, appointment time, action type; Export button
- Action type colour coding: create (green), edit (amber), delete (red), status (blue)
- Exportable to CSV with all fields
