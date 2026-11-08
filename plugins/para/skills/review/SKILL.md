---
name: review
description: Run the weekly review of the user's Notion PARA system and list what needs a decision. Use when the user asks for a weekly review, what is stale or overdue, what to clean up in PARA, or the state of their projects.
---

# Weekly review

The user's PARA system is one Notion database called **System**, under a page called **P.A.R.A. method**.
Find it the way the `capture` skill does: search for the database titled `System` whose path includes `P.A.R.A. method`, fetch it, and note each data source's `collection://` URL by title.

Use the Notion MCP tools.
If they are missing or unauthorized, tell the user to connect Notion with `/mcp` and stop.

## 1. Collect

Query each data source and keep only these rows:

- **Projects**: Status is Active, Blocked or On Hold, and the Deadline has passed, there is no Deadline, or Updated is more than 7 days ago.
- **Projects**: more than 7 rows with Status Active. PARA works best with 3 to 7.
- **Readings**: Status is Unread and Created is more than 30 days ago.
- **Infra**: Monitor is ticked, Retired is not, and Status is not Up, or Last checked is more than a day ago.
- **Skills**: Status is Trying and Updated is more than 14 days ago.
- **Docs**: Status is Published and Updated is more than 180 days ago.

The Projects linked view has a **Review** tab and the Resources one a **Stale** tab with the first and third filters; use them when the query tool accepts a view.

## 2. Report

Group the rows under one heading per data source, skipping empty ones.
For each row give its name as a link, why it is listed, and one suggested action:

- Overdue or undated project: set a new Deadline, or move to On Hold, Done or Dropped.
- Quiet project: name the next step, or move to On Hold.
- Old unread reading: read it this week, or set Status to Archived.
- Unhealthy service: open its Error and Deployment links; tick Retired if it is gone.
- Stale trial skill: Installed or Removed.
- Old doc: review it, or set Status to Superseded.

End with one line of counts, for example `3 projects, 5 readings, 1 service need a decision`.
If nothing is listed, say the system is clean.

## 3. Apply

Change nothing until the user picks actions.
Then update only the rows and properties they chose, never delete a row, and never write columns the PARA Worker syncs.
