# Triage Labels

The skills speak in terms of five canonical triage roles. This file maps those roles to the actual label strings used in this repo's issue tracker.

| Label in mattpocock/skills | Label in our tracker | Meaning                                  |
| -------------------------- | -------------------- | ---------------------------------------- |
| `needs-triage`             | `needs-triage`       | Maintainer needs to evaluate this issue  |
| `needs-info`               | `needs-info`         | Waiting on reporter for more information |
| `ready-for-agent`          | `ready-for-agent`    | Fully specified, ready for an AFK agent  |
| `ready-for-human`          | `ready-for-human`    | Requires human implementation            |
| `wontfix`                  | `wontfix`            | Will not be actioned                     |

When a skill mentions a role (e.g. "apply the AFK-ready triage label"), use the corresponding label string from this table.

All five strings are identical to the canonical role names, so no translation is needed in practice. `wontfix` already existed as a GitHub default label; the other four were created by `/setup-matt-pocock-skills`.

Edit the right-hand column to match whatever vocabulary you actually use.

## Category labels

Triage also uses two **category** roles, which are plain GitHub defaults in this repo:

| Role          | Label in our tracker |
| ------------- | -------------------- |
| `bug`         | `bug`                |
| `enhancement` | `enhancement`        |

Every triaged issue should carry exactly one category role and one state role.

## Wayfinder labels

Used by `/wayfinder` (installed):

| Purpose                        | Label                  |
| ------------------------------ | ---------------------- |
| The map (canonical artifact)   | `wayfinder:map`        |
| Ticket type: research (AFK)    | `wayfinder:research`   |
| Ticket type: prototype (HITL)  | `wayfinder:prototype`  |
| Ticket type: grilling (HITL)   | `wayfinder:grilling`   |
| Ticket type: task (HITL or AFK)| `wayfinder:task`       |

These five exist in the tracker as freeform labels (`gh label create`).
