# Testplanner

A standalone, single-file test planning web application for scheduling tester resources, managing test phases and test objects, and visualizing assignments on an interactive timeline.

No server, no build step — just open `index.html` in a browser.

## Features

- **Interactive Timeline** — day-level horizontal timeline with month labels, weekend/today/non-plannable day highlighting, zoom in/out, and click-drag panning
- **Resource Planning** — create planning entries by assigning test objects to testers within test phases; visualized as colored, draggable, resizable bars
- **Master Data Management** — full CRUD for testers, phases, and test objects with activate/deactivate toggles; inactive items hidden from planning
- **Conflict Detection** — automatic detection of overlapping tester assignments (pulsing red outline + conflict panel) and phase overlap prevention
- **Configurable Settings** — working days, phase colors, display toggles (weekend/today highlights, timeline range)
- **Property Panel** — double-click any planning bar to edit all fields in a side panel with Apply, Cancel, and Delete
- **Data Persistence** — automatic save to browser storage (localStorage + OPFS), optional save to a real JSON file via File System Access API, export/import, and reset to defaults

## Usage

1. Open `index.html` in a modern browser (Chrome/Edge recommended for full File System Access API support)
2. Use the **Planning** tab to view and manage the timeline
3. Use the **Master Data** tab to manage testers, phases, and test objects
4. Use the **Settings** tab to configure working days, phase colors, display options, and save file location
5. Click **Save** to persist data — data is always saved locally; use Settings → Change File to save to a real JSON file

## Data Model

| Entity | Fields |
|--------|--------|
| Tester | Id, Name, Email, Team, Active |
| Phase | Id, Name, Description, Sequence, Color, Lead Time, Processing Time, Active |
| Test Object | Id, Name, Description, Status, Priority, Active |
| Planning Entry | Id, TestObjectId, TesterId, PhaseId, StartDate, EndDate, Comment |

## Requirements

- A modern web browser (Chrome, Edge, Firefox, Safari)
- No server, no internet (once loaded), no Node.js, no build tools
