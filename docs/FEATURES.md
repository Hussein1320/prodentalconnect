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
- **NHS Wales Claims** — Wales-specific claim workflow
- **NHS Wales Advanced** — ACORN, CP Engine, Lab Fee, Referral, and Incomplete Work workflows
- **NHS Wales Reconciliation** — reconciliation against BSA payment schedules
- **NHS England Apr 2026** — new contract compliance tools
- **NHS CDS Compliance** — CDS submission and compliance checking
- **NHS Denture Repair** — denture repair claim workflow
- **NHS Northern Ireland (NI)** — NI-specific claim management
- **NHS UDA Report** — detailed UDA activity export
- **NHS Claim Compliance** — cross-region claim compliance checking
- **NHS Regional Routing** — route claims to correct regional BSA gateway
- **NHS Enterprise** — multi-practice NHS contract management
- **NHS Regional Architecture** — infrastructure configuration for multi-site NHS setups

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

The Super Admin role is reserved for ProDentalConnect platform administrators. Super Admins see a separate admin sidebar with tools for managing all practices, subscriptions, platform AI, system monitoring, security, cloud backup, support tickets, software updates, and announcements. Super Admin login always requires 2FA.

---

*For technical support, use the Help & Support page within the app or email support@prodental.co.uk*
