<!-- Reader: notebook users and security researchers. Effect: report a security issue privately. -->
# Security

Report security issues to [security@warfarecommand.com](mailto:security@warfarecommand.com). Send the product and version, affected feature, expected boundary, and steps to reproduce with fictional data. Keep notebook links, credentials, names, identifiers, and records out of the report. Do not post a security issue publicly before the maintainer has reviewed it. No response time is promised.

Leader's Notebook stores private data under `data/users/<id>/ln/`. Shared paths contain status, the program document, and installation metadata. Read-only viewers cannot write. Artifact `db` rules, private-path enforcement, and separate account tests establish that boundary. A local mock is not proof of production enforcement.

Setup and pasted updates verify exact file bytes against SHA-256 hashes in the public release manifest. The release repository is the trust root, with publisher rules and push protection. A compromised repository can replace files and matching hashes. That is an accepted residual risk. Per-file hashes are not a digital signature. This release has no mutable feed, telemetry endpoint, registration, or automatic update channel. Never bypass a failed hash check.

Use the notebook for Marines you lead. Keep Social Security numbers, medical details, protected communications, classified information, and CUI out of it. Records your command requires stay in your command's system.

## Permission and deletion controls

The page awaits user.canEdit() before subscribing to private collections or enabling owner actions. It does not write a permission probe document. Generic data-write permission alone does not grant owner mode. Read-only shares show status and the shared program. Live owner, Contributor, and viewer accounts must still verify the platform rules.

Automatic full reset is unavailable for saved notebooks. Legacy interrupted reset plans restore missing documents and preserve changed holds. Archive keeps private entries; Delete records is a separate choice on an archived Marine. Deletion checks holds fresh and verifies each removal. A new hold stops removal and reports the documents already removed; the platform has no atomic conditional deletion, so a hold entered during deletion is an accepted residual risk.


## Current platform limits

Private page documents use `data/users/<uid>/ln/<kind>/<id>` and collections use `data/users/<uid>/ln/<kind>`, built from document and collection refs. Await `user.id()`. Document paths have an even segment count; collection paths have an odd count. Snapshots expose an `exists` boolean and `data()` returning a frozen body. Clone that body before editing. Owner controls require `user.canEdit()`; another viewer's private subtree remains invisible. Chat ArtifactData uses `data/users/me/ln/` for this same namespace.

Word exports read the Marine fresh and refuse a legal hold before generation and the save prompt. A successful save resolves `{status:"saved"}`; `{status:"delivered"}` means delivery to a requested destination, not a saved copy. A decline rejects with `declined` and does not retry. Archive keeps private entries and removes active/shared status. Reactivate restores the Marine. Delete records is a separate choice on the archived Marine page. After the saved Marine copy and your confirmation, deletion compares fresh covered contents to the accepted copy, checks the hold, deletes covered documents with readback, and regenerates the program from permitted fields. Changed or new covered documents require a new Marine copy. If a new hold appears, removal stops and lists exactly which documents were removed and which remain. A hold entered on another device during a save prompt or between a hold check and deletion can arrive too late to prevent that save or deletion. These are accepted residual risks; review holds before exporting or deleting records.
