# ShelfSense 🛒

A shelf-monitoring prototype that turns availability issues into actionable staff tasks and verifies recovery.

Built by **Team Kernel Panic**.

## Problem

Manual shelf checks can leave empty shelves, low availability, and misplaced products unnoticed. Staff also need a clear way to track issues and confirm that they have been fixed.

## Features

- Detect simulated empty shelves and low visible stock.
- Flag products placed in the wrong shelf zone.
- Confirm issues after three clear observations.
- Treat blocked camera views as **UNKNOWN**, not empty.
- Create one open task per zone and issue type.
- Allow staff to acknowledge tasks or report unavailable backroom stock.
- Close tasks only after three clear recovery observations.
- Show an activity timeline and export incident reports as JSON.
- Save demo state in the browser using localStorage.

## Try the Demo

Click **Run guided demo** to see the complete workflow:

1. Stock is removed while the view is blocked.
2. The view clears and the shortage is confirmed.
3. A task appears in the staff queue.
4. Staff acknowledge the task.
5. Products are restocked.
6. Three healthy observations verify recovery and close the task.

You can also select a shelf zone and manually remove products, misplace an item, block the view, or disconnect the simulated camera.

## Technology

- HTML5
- CSS3
- Vanilla JavaScript
- Browser localStorage

No installation, API keys, or build tools are required.

## Run Locally

Download the repository and keep these files together:

```text
ShelfSense/
├── index.html
├── app.js
└── README.md
```

Open `index.html` in a browser.

## Deploy with GitHub Pages

1. Upload `index.html` and `app.js` to the repository root.
2. Open **Settings → Pages**.
3. Select **Deploy from a branch**.
4. Choose **main** and **/ (root)**.
5. Save and wait for GitHub to provide the website link.

## Prototype Rules

| Setting | Value |
| --- | --- |
| Shelf zones | 6 |
| Simulated sampling interval | 2 seconds |
| Minimum visible quantity | 2 units per zone |
| Issue confirmation | 3 clear samples |
| Recovery confirmation | 3 clear samples |
| Prolonged obstruction alert | 20 seconds |
| Unresolved task reminder | 60 seconds |

Sampling runs while the page is open and sampling is enabled. Background browser tabs may slow timers.

## Current Limitations

This is an interactive workflow simulation.

- No live camera or trained YOLO model is connected.
- Product counts and shelf events are controlled through demo buttons.
- Evidence is a simulated observation record, not a camera photograph.
- Tasks and history are stored locally in each browser.
- Staff actions are simulated; there are no shared accounts.
- Reminders appear inside the app; phone notifications are not connected.
- Visible shelf availability does not represent hidden or backroom inventory.

## Planned Real-Camera Integration

- Capture frames from a fixed shelf camera.
- Train and validate a product detector for 6–8 SKUs.
- Map detections to configured shelf zones.
- Handle obstructed views and uncertain predictions.
- Store incidents and evidence images in a backend.
- Add shared staff access and notifications.
- Evaluate detection accuracy, false alerts, and recovery latency.

## Team Kernel Panic

- Aryan Mendpara — Team Lead
- Dheer Mehta
- Darshil Savaliya
- Aryan Tiwari

---

**One issue. One task. Verified recovery.**
