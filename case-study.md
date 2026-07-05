# Case Study: FIELDWAVE SF Policy Radar

## Executive Summary

FIELDWAVE SF Policy Radar is a lightweight civic intelligence workflow that monitors San Francisco legislative agendas for arts, culture, creative economy, cultural infrastructure, and adjacent policy signals. The system was designed to reduce manual agenda scanning, surface relevant items earlier, and preserve human-in-the-loop policy judgment in a structured review process.

The public version of this case study intentionally focuses on the problem, product strategy, architecture pattern, and outcomes. It does not disclose private credentials, live workspace data, stakeholder-specific notes, proprietary scoring refinements, or future roadmap details.

## Problem

Cultural policy is rarely labeled cleanly. Relevant issues can appear inside budget appropriations, land use actions, permitting changes, workforce items, public space rules, technology governance, economic development programs, or equity initiatives.

For practitioners, the challenge is not simply finding items that say "arts" or "culture." The challenge is recognizing when a broader civic action may affect artists, venues, cultural districts, creative workers, community-serving nonprofits, or public cultural infrastructure.

Manual monitoring creates several operational risks:

- Important items can be missed when they are embedded in broader agendas.
- Staff time is spent repeatedly scanning public pages instead of evaluating policy implications.
- Institutional memory is fragmented across emails, notes, spreadsheets, and meeting prep documents.
- Automation can become counterproductive if it overwrites expert judgment or floods reviewers with low-value matches.

## Product Goal

The goal was to create a portfolio-quality prototype that demonstrates how civic data, policy expertise, and workflow design can be combined into a practical review queue.

The system needed to be:

- Useful: surface culturally relevant policy signals early enough for review.
- Explainable: show why an item may matter, not just that it matched a keyword.
- Lightweight: run without heavy infrastructure or a custom application stack.
- Human-centered: preserve manual policy analysis after the first automated pass.
- Portable: establish a pattern that could be adapted to other jurisdictions or policy domains.

## Solution Overview

The monitor scans current and recent San Francisco public Legistar agendas, enriches matching agenda items from linked detail pages, classifies policy signals, and publishes structured records into a Notion review database.

A preservation wrapper protects manually edited judgment fields so automated updates can refresh factual information without erasing a reviewer’s analysis.

At a high level, the workflow is:

1. Collect recent public meeting agenda links.
2. Parse agenda items and associated Legistar file numbers.
3. Enrich each item with detail-page metadata and action history when available.
4. Apply a cultural policy taxonomy and impact triage logic.
5. Create or update Notion records keyed by file number.
6. Preserve selected manual review fields on subsequent updates.
7. Run daily through GitHub Actions or manually in dry-run mode.

## Architecture Pattern

The architecture can be summarized as:

1. Public San Francisco Legistar agendas
2. Agenda parser and detail-page enricher
3. Policy signal classifier and triage rules
4. Credential-free dry-run output or Notion export
5. Review queue that preserves human edits

The architecture deliberately avoids treating public records as a full data warehouse. Instead, it acts as a targeted policy triage layer that helps reviewers decide what deserves attention.

## Key Design Decisions

### Agenda-first monitoring

The project uses current public agenda pages as the operational source for recent monitoring because agenda pages are closer to the review workflow and can surface items before slower or less reliable public API paths are complete.

### Human-in-the-loop preservation

The system separates factual updates from human judgment.

Factual fields such as latest action, status, dates, sponsors, committees, and source links can continue to update.

Judgment fields such as category, urgency, policy signal, impact level, and why-it-matters language are protected after manual review.

### Triage over exhaustive capture

The project is not designed to mirror every public record. It is designed to identify likely cultural policy relevance and route those items into a review process.

This keeps the tool focused on decision support rather than archival completeness.

### Public demo without credentials

A dry-run mode allows the workflow to be demonstrated without exposing Notion secrets or writing to a live database.

This makes the project safer to share during job applications and interviews.

## Skills Demonstrated

- Civic data workflow design
- Legislative monitoring and policy operations
- Product scoping for a real practitioner workflow
- Python data extraction and enrichment
- Taxonomy design and signal classification
- Human-in-the-loop automation design
- GitHub Actions automation
- Credential hygiene and portfolio-safe documentation
- Translating ambiguous policy needs into maintainable tooling

## Example Interview Narrative

"I built FIELDWAVE SF Policy Radar to solve a practical policy operations problem: cultural policy signals often appear inside broader legislative items, and manual agenda scanning is time-consuming.

I designed a lightweight monitor that scans public San Francisco agenda pages, enriches matching items, classifies the policy signal, and routes the result into a structured review queue.

A key design choice was preserving human judgment fields after manual review, because in policy work the automation should support expert interpretation rather than overwrite it.

The public case study shows the architecture and decision logic while keeping credentials, live workspace data, and proprietary roadmap details private."

## Public-Safe Outcomes

This package can be used to demonstrate:

- A working prototype that connects public civic data to an operational review workflow.
- An understanding of how to balance automation with expert judgment.
- A product mindset focused on user workflow, not just data collection.
- A privacy/IP-aware approach to portfolio presentation.

## What Is Intentionally Not Included

To protect ongoing product development, this public case study does not include:

- Notion credentials or database identifiers.
- Screenshots of private review queues or stakeholder annotations.
- Proprietary prioritization refinements that are still being tested.
- Unreleased roadmap details.
- Private notes about partners, funders, advocacy strategy, or commercialization plans.
