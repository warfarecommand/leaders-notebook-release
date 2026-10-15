<!-- Reader: Marine leaders. Effect: set up a notebook and understand its limits. -->
# Leader's Notebook

Counseling and mentorship for Marines you lead. Track counseling dates, write your records, and review each Marine's goals in your own Claude account.

Version 0.1.3 uses pack `usmc-counseling-2026.10`. Warfare Command publishes the notebook. Anthropic hosts it under your login. Warfare Command has no account on it and receives nothing from it. This release has no telemetry, registration, or usage counts.

## Set up your notebook

Claude Pro or higher is required to save this notebook. Warfare Command adds no charge. Send this message in a new Claude chat:

```text
Set up Leader's Notebook for me. Read https://raw.githubusercontent.com/warfarecommand/leaders-notebook-release/main/SETUP.md and follow it.
```

Claude verifies the release files and finds your existing notebook before publishing. Tap Publish when Claude asks. Open your notebook to answer its setup cards. If setup stops, return to the same chat or send the same message in another chat. Keep the same notebook address.

## What it does

- Today shows the next sessions, late counseling, events, and targets.
- Marines holds people and your relationships to them.
- Calendar shows counseling and evaluation dates alongside absences.
- Sessions takes a record through prep, writing, review, delivery, acknowledgment, and filing. Later changes to a frozen record become amendments.
- More holds voluntary mentorship, your counseling program, settings, exports, and Talk to Claude.

The three editable formats are a full counseling record, an NCO worksheet, and a junior Marine worksheet. Dates carry their meaning: a rule deadline from the cited text, a planning target inside its window, or a confirmed event you recorded. Unknown dates remain unknown. Read the cited source and confirm what applies with your command.

Marines Pvt through Col, active and reserve, are supported. Sailors and civilians can use the Marine model; their own service and HR rules are not modeled yet. [Support](SUPPORT.md) explains saving, sharing, and recovery.

## Records and privacy

NAVMC 2795 para 3005.1.i keeps counseling documentation between the senior and junior. It is not forwarded up the reporting chain or passed to the next senior, and it is destroyed when the relationship ends. Archive is the default after closeout counseling and keeps your entries. Reactivate restores the Marine. Delete records is a separate later choice. Export as necessary. A legal hold pauses export and destruction; consult admin and the SJA.

A read-only share shows status and the program document. Records, notes, targets' text, and mentoring stay private. Anyone using your login can read your notebook. The GenAI.mil packet carries cited rules, three Word and Markdown templates, blank record and session schemas, fictional examples including adverse routing, and verify/CHECKS.md. It also carries your verbatim standing guidance, custom template labels, and the optional roster. Roster names read Last, First MI, and next due uses the 12 OCT 2026 date format. Records, notes, and mentoring never enter it. Use the packet and PROMPT.txt, then run the checks to find out whether the receiving model can reuse the skill in a new session. Review every export before moving it.

Use the notebook for Marines you lead. Keep Social Security numbers, medical details, protected communications, classified information, and CUI out of it. Records your command requires stay in your command's system.

Read [privacy and deletion](PRIVACY.md). Adverse matters use the routing card; the notebook never drafts a 6105 entry or a page 11.

## Update at the same address

```text
Update Leader's Notebook for me. Read https://raw.githubusercontent.com/warfarecommand/leaders-notebook-release/main/UPDATE.md and follow it.
```

Claude verifies all release files and shows the changes before updating the same artifact URL. Your personal data stays. Leader's Notebook uses this pasted update path.

The [product page](https://warfarecommand.com/leaders-notebook/) has setup and help. The [public release repository](https://github.com/warfarecommand/leaders-notebook-release) holds verified installation files. See [security](SECURITY.md) for private reports. Propose changes through the [public repository's issues](https://github.com/warfarecommand/leaders-notebook-release/issues).

Warfare Command is unofficial and not affiliated with the Department of Defense or the Marine Corps. Nothing here is legal, financial, or medical advice. MIT license, copyright Warfare Command.


## Current platform limits

Private page documents use `data/users/<uid>/ln/<kind>/<id>` and collections use `data/users/<uid>/ln/<kind>`, built from document and collection refs. Await `user.id()`. Document paths have an even segment count; collection paths have an odd count. Snapshots expose an `exists` boolean and `data()` returning a frozen body. Clone that body before editing. Owner controls require `user.canEdit()`; another viewer's private subtree remains invisible. Chat ArtifactData uses `data/users/me/ln/` for this same namespace.

Word exports read the Marine fresh and refuse a legal hold before generation and the save prompt. A successful save resolves `{status:"saved"}`; `{status:"delivered"}` means delivery to a requested destination, not a saved copy. A decline rejects with `declined` and does not retry. Archive keeps private entries and removes active/shared status. Reactivate restores the Marine. Delete records is a separate choice on the archived Marine page. After the saved Marine copy and your confirmation, deletion checks the hold, deletes covered documents with readback, and regenerates the program from permitted fields. If a new hold appears, removal stops and lists exactly which documents were removed and which remain. A hold entered on another device during a save prompt or between a hold check and deletion can arrive too late to prevent that save or deletion. These are accepted residual risks; review holds before exporting or deleting records.
