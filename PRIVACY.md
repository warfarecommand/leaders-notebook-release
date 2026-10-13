<!-- Reader: Marine leaders using the notebook. Effect: know who can read data and how to remove it. -->
# Privacy and deletion

Last updated 12 OCT 2026. Applies to Leader's Notebook 0.1.1.

## Where your data lives

Your notebook lives in your Claude account. Anthropic hosts and processes it under your account's terms. Warfare Command has no account on it and receives nothing from it. Leader's Notebook has no telemetry, registration, ingest, or usage counts. The site's Copy and Open in Claude actions send no count.

Names, rank, PMOS, billet, dates, and the record text you write are stored by default. EDIPI and DOR are entered at print unless you choose to store them. Social Security numbers are refused. Keep medical and protected material out. Anyone using your login can read your notebook.

Private records live under `data/users/<id>/ln/`. This includes profile, settings, people, relationships, sessions, targets, notes, mentoring, events, absences, and export receipts. An export receipt records a neutral filename, time, kind, and whether records were included; it holds no exported document. Word files use Counseling Last DDMONYYYY.docx. That filename reveals the Marine's last name.

## Read-only sharing

A read-only share shows each Marine's rank and last name, tier, relationship role, last session date, next due date, late flag, and the program document. It also exposes installation progress and version metadata, which must contain no personal data. Share only with people who need that status.

It hides counseling records, drafts, private notes, targets' text, mentoring, private indexes, Ask context, and diagnostics. Shared viewers cannot edit. The Marine's device review shows one selected record. Keep control of the device; this review is different from sharing the artifact link.

## Claude and public file reads

Ask uses the records permitted in the current view and sends that context to Claude. The first request through the page can ask for Claude's permission. A shared viewer's context is limited to the shared projection. Declining Ask leaves the manual fields available.

Setup and pasted updates fetch public release files from GitHub with plain GETs. Document libraries load from jsDelivr. The site loads fonts from Warfare Command's shared assets. Hosting providers receive ordinary request metadata such as internet address and headers. These requests contain no notebook records, profile, board URL, or install id. Anthropic and hosting providers control their own processing and retention.

## What exports contain

- A single record export contains that reviewed record as Word or copied text, its administrative fields, goals written into it, guidance, certification, and amendments. Identifiers you enter at print appear in that copy.
- A roster and program handoff is available as Word or JSON. It contains the active roster, tier, relationship roles, next due, and program text. The JSON also carries roster ids, names, rank, Marine or other personnel kind, PMOS, BILMOS, component, status, relationship ids, start and end dates, whether the start is known, reported or conducted history, and reporting periods so the relief can review the proposed import. EDIPI, DOR, billet text, personal goals, records, and notes are excluded by default. The program is shared text; review it for personal details. Mentoring is always excluded.
- Choosing Include records and notes adds counseling sessions for that active roster, including their ids, dates, states, versions, record fields, amendments, and acknowledgment, plus private notes. The Word handoff shows the record and note text; the JSON preserves the structured fields. This choice can export multiple records together. Review the scope before deciding an export is necessary under NAVMC 2795 para 3005.1.i.
- Export all records creates a JSON copy of every stored counseling session, including records for archived Marines. It excludes private notes and mentoring. A legal hold blocks any export containing the held Marine.
- The Marine's closeout copy is JSON with their roster fields, counseling sessions, targets, and personal goals. It excludes private notes and mentoring. A legal hold pauses this departure export and destruction until reviewed with admin and the SJA.
- A program export contains the counseling program generated from your setup: roles, cadence sources, overrides, unit rules, drill and annual training dates, forms, weekly review, record handling, your unit header, and text you edited. Review those fields before sharing.
- The GenAI.mil method packet contains instructions, a manifest with hashes, cited rule excerpts, cadence and review rules, the adverse boundary, record handling rules, 3 record templates, standing guidance, schemas, synthetic examples, and verification checks. Its signature block has placeholders to fill on the government side. A second tap can add a roster containing Marine, rank, tier, relationship, and next due. Records, notes, and mentoring never enter the packet. Review templates and standing guidance for personal details before saving or moving it.

Saved exports live wherever you put them. Warfare Command cannot retrieve or delete those copies. Moving a packet through DoD SAFE or loading it into GenAI.mil creates copies governed by those systems and your command's rules.

## Archive and deletion

Archive is the default when a Marine leaves your active roster. Archive Marine keeps every record, note, target, and mentoring entry in your notebook. It removes the Marine from Today, Calendar, counts, the shared status projection, and the generated program roster. Reactivate restores the Marine to your active roster. A legal hold stays on the Marine when archived or reactivated.

Deletion is your choice. On an archived Marine's page, Delete records opens a separate sheet. NAVMC 2795 para 3005.1.i says documentation is for the senior and junior only, is not forwarded up the reporting chain or passed to the next senior, and is destroyed when the relationship ends. Save the Marine's copy first if deletion is appropriate, then confirm destruction. The page reads the legal hold fresh, checks that the copy covers current records, deletes each covered document, and reads it back. A new hold or changed document stops removal and lists what was removed and what remains. Mentoring stays separate and is kept. Downloaded copies remain wherever you saved them. Records required by your command remain in its system under its dispositions.

## How to delete

Preserve any permitted copies you need, subject to a legal hold. Revoke shares and delete the notebook artifact through your Claude account's controls. Verify that the artifact is no longer accessible. Warfare Command cannot delete your notebook or confirm Anthropic's backend retention. Delete chats containing notebook text, local drafts and browser copies, downloaded exports, backups, and shared copies separately. Removing one artifact does not remove those copies. Use the relevant provider's controls for DoD SAFE and GenAI.mil copies.

## Report a problem

Report a problem prepares a local diagnostic for you to review. It contains version, pack, screen, capability states, and recent error classes. It excludes names, service dates, board links, notes, records, values, and stack traces. Nothing is automatically sent. If you choose to email a report to [feedback@warfarecommand.com](mailto:feedback@warfarecommand.com), Warfare Command receives the text you send. Remove personal details first. To request removal of that correspondence, contact [security@warfarecommand.com](mailto:security@warfarecommand.com) from the sending address. Separate inbox, provider, and recipient copies may remain.

## Data boundary

Use the notebook for Marines you lead. Keep Social Security numbers, medical details, protected communications, classified information, and CUI out of it. Records your command requires stay in your command's system.


## Current platform limits

Private page documents use `data/users/<uid>/ln/<kind>/<id>` and collections use `data/users/<uid>/ln/<kind>`, built from document and collection refs. Await `user.id()`. Document paths have an even segment count; collection paths have an odd count. Snapshots expose an `exists` boolean and `data()` returning a frozen body. Clone that body before editing. Owner controls require `user.canEdit()`; another viewer's private subtree remains invisible. Chat ArtifactData uses `data/users/me/ln/` for this same namespace.

Word exports read the Marine fresh and refuse a legal hold before generation and the save prompt. A successful save resolves `{status:"saved"}`; `{status:"delivered"}` means delivery to a requested destination, not a saved copy. A decline rejects with `declined` and does not retry. Archive keeps private entries and removes active/shared status. Reactivate restores the Marine. Delete records is a separate choice on the archived Marine page. After the saved Marine copy and your confirmation, deletion compares fresh covered contents to the accepted copy, checks the hold, deletes covered documents with readback, and regenerates the program from permitted fields. Changed or new covered documents require a new Marine copy. If a new hold appears, removal stops and lists exactly which documents were removed and which remain. A hold entered on another device during a save prompt or between a hold check and deletion can arrive too late to prevent that save or deletion. These are accepted residual risks; review holds before exporting or deleting records.
