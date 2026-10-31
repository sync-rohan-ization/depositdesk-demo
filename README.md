# DepositDesk

### Security Deposit & FDR Lifecycle Management

A browser-based demonstration of a unified workspace for managing security deposits and Fixed Deposit Receipts—from submission and document review to maturity monitoring, clearances, and release tracking.

Built for **Smart India Hackathon — Problem Statement SIH26265**.

**Organization:** AICTE  
**Department:** Regulation Bureau  
**Theme:** Smart Automation

[Open the live demo](https://sync-rohan-ization.github.io/depositdesk-demo/)

> Independent student prototype, not an official AICTE service. All sample records are synthetic. AI outputs and bank verification responses are simulated.

## The problem

Managing an FDR involves more than storing a receipt. Officials need to track document discrepancies, confirmation from authorized sources, maturity dates, replacements, clearances, and release decisions.

DepositDesk demonstrates how these activities can be connected through one institution-linked record, with clear next steps and an activity history.

## Features

| Workspace | What you can explore |
|---|---|
| Work queue | Records and actions requiring attention |
| All deposits | Search, filter, create records, and export CSV |
| Review documents | Compare submitted fields with sample receipt information |
| Release requests | Track clearances, authorization, and completion separately |
| Due dates | Monitor approaching deadlines and generate demo reminders |
| Activity log | Review recorded actions and export history |
| Help & rules | Read workflow guidance and policy references |

Additional demonstration features include:
- Duplicate bank/reference checks
- Renewal and replacement record linking
- Multiple role views
- Sample date advancement for deadline scenarios
- Resettable browser-local sample data

## Try the demonstration

1. Open the [live website](https://sync-rohan-ization.github.io/depositdesk-demo/).
2. Select **Demo walkthrough**.
3. Select **Reset & start walkthrough**.
4. Review the sample discrepancy: the entered amount is ₹35 lakh, while the sample receipt shows ₹30 lakh.
5. Select **Use ₹30 lakh from receipt** to record the correction.
6. Select **Run demo bank check** to see a simulated confirmation.
7. Continue to the release workflow and record the required clearances using the relevant role views.
8. Switch to **Competent authority** to record authorization, then completion.
9. Open **Activity log** to inspect the recorded actions.
10. Explore **Due dates** to test deadline monitoring and reminders.

The role selector is a demonstration control, not a secure authentication mechanism.

## What works today—and what is simulated

| Capability | Current prototype |
|---|---|
| Navigation, search, filters, and forms | Functional in the browser |
| Lifecycle tracking and activity history | Functional with browser-local data |
| Deadline calculations and reminder records | Functional within the demo |
| CSV and history exports | Functional |
| Document extraction and AI findings | Scripted sample outputs |
| Bank verification | Simulated response |
| File selection | Does not upload documents or perform OCR |
| User roles | Interface simulation; no secure login |
| Email and SMS | No messages are sent |
| AICTE and bank integrations | Not connected |
| Release processing | Records a demo workflow; does not move funds |

## Run locally

No npm installation, build step, or API key is required.

Download or clone the repository:

```bash
git clone https://github.com/sync-rohan-ization/depositdesk-demo.git
cd depositdesk-demo
```

Start a local server:

```bash
python -m http.server 8000
```

On systems using `python3`:

```bash
python3 -m http.server 8000
```

Open:

http://localhost:8000

## Project structure

```text
depositdesk-demo/
├── index.html    # Page structure and navigation
├── style.css     # Layout and visual styling
├── app.js        # Sample data and application behavior
└── README.md
```

## Technology

- HTML5
- CSS3
- Vanilla JavaScript
- Browser localStorage
- GitHub Pages hosting

The current demo has no backend or shared database.

## Data storage

Changes are saved in localStorage in the current browser.

- Different visitors have separate demo data.
- Data does not synchronize across devices.
- Clearing browser storage removes saved changes.
- **Reset sample data** restores the demonstration records.

Use synthetic information only. Do not enter real financial or personal records into this public demo.

## Proposed production development

The following capabilities require further implementation and authorized access:

- OCR extraction with field confidence and document evidence
- AI-assisted discrepancy detection with human review
- Authorized bank confirmation connectors and manual fallback
- Integration with existing AICTE institution records
- Secure authentication and server-enforced permissions
- Encrypted document storage and controlled retention
- Server-side audit history and notification delivery
- Versioned policy rules based on applicable requirements

AI findings would support scrutiny. Final verification, regulatory decisions, and release authorization remain with competent officials.

## Evaluation plan

Evaluate the solution against a manual baseline using synthetic or authorized records:

- Review time per instrument
- Extraction accuracy
- Discrepancy detection accuracy
- Time to source confirmation
- Timeliness of deadline alerts
- Completeness of the audit history

These are planned evaluation measures, not claimed performance results.

## Research foundation

The proposed workflow draws on AICTE approval documentation, security deposit/JFDR user manuals, updated addenda, circulars, and procurement documents.

Current internal procedures, integration contracts, bank verification access, and applicable policy configurations require confirmation before production deployment.

## Project status

**Interactive student prototype — suitable for demonstrations and workflow discussion.**

Not a production financial system or an official government portal.
