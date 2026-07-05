# Demo Guide

This guide supports a short public demo of FIELDWAVE SF Policy Radar without exposing credentials or writing to a live Notion database.

## Demo Goal

Show that the project can turn public legislative agenda data into a focused cultural policy review queue while preserving a clear boundary between automated signal detection and human policy judgment.

## Setup

Install the lightweight dependencies.

If your Mac uses a standard Python setup, you may be able to run:

    pip install requests beautifulsoup4

If your Mac uses python3, use:

    python3 -m pip install requests beautifulsoup4

If your Python environment is externally managed, create and activate a virtual environment first:

    python3 -m venv .venv
    source .venv/bin/activate
    python3 -m pip install requests beautifulsoup4

## Credential-Free Preview

Run a dry-run scan with a small limit from the main SF Policy Radar project repository:

    python3 monitor_current_agenda_preserve_manual.py --dry-run --limit 5

For structured output, use JSON mode:

    python3 monitor_current_agenda_preserve_manual.py --dry-run --json --limit 5

## Suggested Talking Points

1. Start with the workflow pain point: cultural policy signals are often buried inside broader civic agendas.
2. Explain the product boundary: the tool is a triage system, not a public-records mirror.
3. Show the dry-run: demonstrate that the system can run without Notion credentials.
4. Call out the human-in-the-loop design: manual judgment fields are preserved after review.
5. Discuss extensibility: the same pattern can be adapted to other jurisdictions or policy domains.

## What Not to Show Publicly

- Live Notion databases containing private notes.
- Environment variables, secrets, database IDs, or API tokens.
- Stakeholder-specific annotations or outreach strategy.
- Unreleased roadmap details or proprietary scoring refinements.

## Short Demo Script

"This is a civic intelligence workflow I built for San Francisco cultural policy monitoring. It scans current public agenda pages, enriches potentially relevant legislative items, applies a cultural policy taxonomy, and can export the result into a review queue.

For a public demo, I use dry-run mode so no credentials are needed and no private workspace data is exposed.

The important product decision is that factual updates can keep flowing, but manual judgment fields are preserved once a reviewer has assessed the item."
