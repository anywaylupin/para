---
name: capture
description: File a link, repo, AI skill, service, note or project into the user's Notion PARA system. Use when the user says save, capture, file, add to PARA, remember this link, track this repo, or start a project, or pastes a URL or owner/repo to keep.
---

# Capture into PARA

The user's PARA system is one Notion database called **System**, under a page called **PARA Dashboard**.
It holds eight data sources: Projects, Areas, Repos, Skills, Infra, Readings, Docs and Prompts.
Every capture becomes one row in one of them.

Use the Notion MCP tools.
If they are missing or unauthorized, tell the user to connect Notion with `/mcp` and stop.

## 1. Find System

Search Notion for the database titled `System`.
Take the result whose parent page is titled exactly `PARA Dashboard`; if there are several or none, ask the user which one.
Fetch it once and note the `collection://` URL of each data source by its title.
Reuse those URLs for the rest of the session.

## 2. Pick the data source

| The user has                                         | Data source | Fill in                                     | Status                                    |
| ---------------------------------------------------- | ----------- | ------------------------------------------- | ----------------------------------------- |
| An outcome with an end date                          | Projects    | Name, Priority, Deadline, Areas             | Backlog, or Active if they start now      |
| An ongoing responsibility                            | Areas       | Name                                        | Active                                    |
| A link to read, watch or take later                  | Readings    | Name, Link, Type                            | Unread                                    |
| A GitHub repo they build or watch                    | Repos       | Key as `owner/repo`, Origin                 | Planned for their own, Watching otherwise |
| An AI skill, plugin, MCP server or agent             | Skills      | Name, Kind, Source as `owner/repo`, Slug    | Discovered                                |
| A deployed service or account                        | Infra       | Name, Provider, Resource ID, Monitor ticked | Unknown                                   |
| Writing to keep: notes, how-tos, specs, explanations | Docs        | Name, Diátaxis                              | Draft                                     |
| A prompt they reuse with an AI tool                  | Prompts     | Name, Prompt (the full text), Category      | Draft, or Ready once it works             |

Fetch the chosen data source before writing, and use its exact property names and option values.
When the input fits two rows of the table, ask one short question instead of guessing.

## 3. Check for a duplicate

Search the chosen data source for the same thing: the same Link for Readings, Key for Repos, Source and Slug for Skills, Resource ID for Infra, a near-identical Prompt for Prompts, or a near-identical Name.
If a row exists, update it instead of adding a second one, and say so.

## 4. Create the row

- Use the data source's template that matches the row when the tool can apply it: New Project, Build or Learn; Article, Video, Book or Course; OSS repo, Planned repo or Fork; New Skill, New Plugin, New MCP server or New Agent; Tutorial, How-to, Reference or Explanation; New prompt.
- Set Status from the table.
- Link the row to the project or area it serves when the user names one or it is obvious from the conversation; search Projects and Areas by name to get the page URL. Leave both empty otherwise.
- Never fill columns the PARA Worker syncs: Infra Status, Deployment, Domain, Last deploy, Deploy state, Last checked and Error; Repos and Skills GitHub, Description, Stars, Version and the other GitHub columns. Write only Key or Source and let the sync fill the rest.
- Never delete rows. To archive, change the status into its Complete group.

## 5. Report

Reply with one line per row: the data source, the row name as a link, and any relation you set.
Mention anything you left for the sync to fill.
