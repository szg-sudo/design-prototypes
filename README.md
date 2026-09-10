# Account transfer and Manage account: interactive prototypes

Two working prototypes from a Coalition insurance product problem: moving an account, or specific quotes and policies, from one broker to another.

Shared with Coalition's permission.

## Open them

Both are single self-contained HTML files. Double click either one, or open the hosted links below. Nothing to install and nothing to build.

| | What it shows |
|---|---|
| `01-account-transfer.html` | The integrated prototype. A real account page wired to the transfer modal, with every entry point live: the header kebab, the quote row menus, and the bulk action bar. |
| `02-manage-account.html` | The modal on its own, with a toggle between a single line account and a multi line account, so both scenarios can be walked without hunting for them. |

Use the **Tweaks panel** to switch scenarios. It exposes the account line configuration, the destination account match states, and the permission gated advanced controls, so you can reach the edge cases directly rather than clicking toward them.

## What the prototypes resolve

The starting problem was that ownership changes and item moves had grown into separate flows with overlapping entry points, and neither one made the consequence of the transfer visible before the user committed.

The direction here does three things:

**One modal, two tabs, one grammar.** Change ownership and Transfer items share a header, a horizontal `From to To` handoff, and a live footer that states the impact as it changes. The active tab communicates the mode, so the two flows stay legible as one idea.

**Progressive disclosure tied to the data, not to a preference.** The account line selector appears only when the account actually has multiple lines. Ownership rules are always present but collapsed to a single expandable link, with the active rule shown inline when collapsed.

**Destination handling that pre-empts the error.** Once a broker is picked, the flow checks for an existing account on the destination side. If matches exist, submission is gated until one is chosen or a new account is created, which is the step that previously produced duplicate accounts.

Full decision record, including the open question still outstanding on the quote row menu, is in `CLAUDE.md` in the source project.

## How these were built

These were built in code as design artifacts, using AI assisted tooling to go from direction to a working, clickable prototype rather than a static mockup. React and Babel run in the browser from a CDN, there is no build step, and the intent throughout was fidelity of behaviour: real state, real edge cases, real empty and error conditions, at a level a static file cannot carry.

They are prototypes rather than production code. They exist to make an interaction argument testable and reviewable by engineers and stakeholders before anything is committed to a sprint.

## A note on the design system

The visual layer uses Coalition's design tokens, spacing scale and component patterns. The licensed display typeface used in the internal build has been removed from these copies and the type is set in Public Sans, which is open licensed. Everything else renders as designed.
