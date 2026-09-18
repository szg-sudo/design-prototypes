# Account transfer and Manage account: interactive prototypes

### → [Open the live prototypes](https://szg-sudo.github.io/design-prototypes/)

The files in this repository are source. The links below open the running versions.

Two working prototypes from an internal insurance product problem: moving an account, or specific quotes and policies, from one broker to another.

## Open them

Both are single self-contained HTML files. Nothing to install and nothing to build.

### ▶ [1. Account transfer, the integrated prototype](https://szg-sudo.github.io/design-prototypes/01-account-transfer.html)

A real account page wired to the transfer modal, with every entry point live. Open the **⋮** menu on the account header, the **⋯** on any quote row, or tick two or more quote rows to use the bulk action bar.

Use the **Tweaks panel**, bottom right, to switch scenarios. It exposes the account line configuration, the destination account match states, and the permission gated advanced controls, so you can reach the edge cases directly rather than clicking toward them.

### ▶ [2. Manage account, the modal on its own](https://szg-sudo.github.io/design-prototypes/02-manage-account.html)

The modal in isolation, with a scenario toggle between a single line account and a multi line account, so both can be walked without hunting for them. Click **Manage account** to open it. Both tabs work: search a broker or account, pick lines and items, expand ownership rules, create a new account, and submit.

Best viewed on a desktop browser at 1280px or wider.

## What the prototypes resolve

The starting problem was that ownership changes and item moves had grown into separate flows with overlapping entry points, and neither one made the consequence of the transfer visible before the user committed.

The direction here does three things:

**One modal, two tabs, one grammar.** Change ownership and Transfer items share a header, a horizontal `From to To` handoff, and a live footer that states the impact as it changes. The active tab communicates the mode, so the two flows stay legible as one idea.

**Progressive disclosure tied to the data, not to a preference.** The account line selector appears only when the account actually has multiple lines. Ownership rules are always present but collapsed to a single expandable link, with the active rule shown inline when collapsed.

**Destination handling that pre-empts the error.** Once a broker is picked, the flow checks for an existing account on the destination side. If matches exist, submission is gated until one is chosen or a new account is created, which is the step that previously produced duplicate accounts.

## How these were built

These were built in code as design artifacts, using AI assisted tooling to go from direction to a working, clickable prototype rather than a static mockup. The intent throughout was fidelity of behaviour: real state, real edge cases, real empty and error conditions, at a level a static file cannot carry.

They are prototypes rather than production code. They exist to make an interaction argument testable and reviewable by engineers and stakeholders before anything is committed to a sprint.
