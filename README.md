# DepositDesk demo website

A browser-based security deposit / FDR lifecycle demonstration for SIH26265.
This package contains the working website source, separate from the presentation.

## Files

- index.html: page structure, navigation and dialogs.
- style.css: work queue, tables, review interface and responsive layouts.
- app.js: synthetic records, validation, document comparison, workflow, reminders and activity history.

No npm packages, build step, API keys or database are required.

## Run locally

1. Extract this ZIP.
2. Open a terminal inside the DepositDesk-Demo folder.
3. Start a local server:

   Windows: python -m http.server 8000
   macOS/Linux: python3 -m http.server 8000

4. Open http://localhost:8000 in your browser.
5. Stop the server with Ctrl+C when finished.

You can also open index.html directly in a modern browser. A local server is recommended for consistent browser storage behavior. If port 8000 is occupied, use another port, such as 8080.

## Demonstration: about four minutes

Use Demo walkthrough > Reset & start walkthrough to restore the initial sample and open the review screen.
Starting the walkthrough resets synthetic changes stored by this demo in the current browser.

1. Show FDR-2026-0142: entered amount INR 35 lakh, receipt amount INR 30 lakh.
2. Click Use INR 30 lakh from receipt (the button displays the rupee symbol). Explain that the previous value remains in the activity log.
3. Click Run demo bank check. Explain that matching a document and confirming the issuing source are separate events.
4. Click Next: release. As Regulation officer, record the Regulation clearance. PGRC clearance is pre-completed in the synthetic sample.
5. Change Viewing as to Vigilance officer and record its clearance.
6. Change Viewing as to Competent authority. Record authorization. Show that completion remains pending, then record completion separately.
7. Open Activity log and show the responsible roles and sequence of actions.
8. Open Due dates and click Generate due reminders twice. After completing the sample release, the first run creates two reminder records and the second creates zero duplicates, provided no other sample records or dates were changed.

## Additional demonstrations

- All deposits: search, filter, add a synthetic record and export CSV.
- Submission form: matching bank/instrument references are rejected as duplicates; maturity must be later than issue date.
- Due dates: advance the demonstration clock; this does not change the computer date.
- Conditional replacement: use Regulation officer or Institution user, select Record conditional replacement and enter a new reference, dates and reason. The new pending instrument retains a link to its predecessor.
- Activity log: export the event history as JSON.
- Help & rules: curated reference content with source links.

## How data works

Sample state is saved in browser localStorage under sih26265-lifecycle-v1.
Use Reset sample data to restore the original records. Different origins, ports or browsers have separate storage.
To edit the initial data, change initial() in app.js, then reset the sample in the UI.

## Scope

The interface and browser-local workflows are functional. OCR values, bank responses and case summaries are synthetic or scripted. Selecting a document does not upload it or perform OCR. No real AICTE integration, bank verification, payment, email or SMS occurs.

Viewing as is a demonstration role switch, not secure authentication. Production would require server-enforced permissions, secure storage, authorized source connectors and a validated policy register.

## Editing

Change index.html for layout, style.css for visual design, and app.js for records and behavior. Reload the browser after editing. The code uses standard browser APIs and has no bundled third-party libraries.

## Deploying elsewhere

The three source files can be hosted together on any static web host. The local Python server is only for development. This ZIP excludes hosted-service configuration, credentials and Git metadata.
