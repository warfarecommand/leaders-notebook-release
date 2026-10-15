<!-- Reader: Marine leaders. Effect: recover setup or saving at the same notebook address. -->
# Setup help and supported situations

Leader's Notebook 0.1.3 uses pack `usmc-counseling-2026.10`.

## Supported situations

Marines Pvt through Col, active and reserve. Your role as supervisor, JEPES first line supervisor or evaluator, or FITREP Reporting Senior changes the applicable clocks. Unknown relationship dates remain unknown. Reserve scheduling can use your drill and annual training dates. Unit requirements need their citation and effective date; a local rule cannot relax a binding baseline rule.

Sailors and civilians can be added using the Marine cadence and record formats. Their own service and HR counseling rules are not modeled yet. Confirm applicable requirements with the service personnel office or HR before using that model.

## Finish setup

Claude Pro or higher is required to save the notebook. Warfare Command adds no charge. Claude Free cannot save notebook data. A missing capability alone does not establish your plan or account status.

Send this in a new Claude chat:

```text
Set up Leader's Notebook for me. Read https://raw.githubusercontent.com/warfarecommand/leaders-notebook-release/main/SETUP.md and follow it.
```

Setup checks all artifacts for the notebook identity, updates one existing notebook in place, asks you to choose if several exist, and creates a new notebook if none exists. Tap Publish when Claude asks, then open your notebook. The page asks who you are, who you lead, how your unit runs, and your standing guidance. Give what you know; change it later in Settings. Keep the notebook private.

If the chat closes, send the same message in another chat. Claude finds the existing notebook. Open the same URL to resume its setup cards. Never publish another notebook to recover. If more than one exists, select the address you use.

Two setup chats run at the same moment can create two notebooks. Keep the one with your saved work. Review the other for any work you need, revoke its shares, then delete the extra artifact through your Claude account. If the extra contains a Marine on legal hold, consult admin and the SJA before removing it.

## Phone app and tools

If the phone app cannot open the artifact or the chat has no artifact tools, sign in to the owning account at [claude.ai in your phone browser](https://claude.ai/). Copy the setup message if Open in Claude leaves it blank. Tool availability in a chat and permission to save data are separate. Do not repeatedly grant a declined permission.

## Recover a failed save

Saved means the page read the write back and it matched. Preserve any unsaved text on the original device before a reload or update. Copy changes into your own account if offered. Do not put private text in a problem report.

- Saving unavailable: check the owning login and artifact permissions. If Claude Free is confirmed, Pro or higher is required. Never infer Free from a failed request.
- Read-only: open the owner's view to edit. A shared viewer cannot write.
- Temporary failure: preserve the draft and retry once. If it still fails, copy the diagnostic and report the problem.
- Conflict: read the current saved values and compare them with your draft. Choose deliberately; never overwrite a concurrent edit without review.
- Storage full or invalid change: preserve the draft and ask for help. Do not delete records automatically or retry a malformed write repeatedly.
- Refresh stopped: preserve the draft and reload the same URL once. Repeating a write does not repair a stopped subscription.
- Ask or downloads unavailable: continue with manual fields. Keep the record; a declined download does not delete it. Use Talk to Claude for help with a reviewed record in your own account.

## Update your notebook

Send this message in a Claude chat:

```text
Update Leader's Notebook for me. Read https://raw.githubusercontent.com/warfarecommand/leaders-notebook-release/main/UPDATE.md and follow it.
```

Claude checks every release file, shows the changes, and asks once before replacing the page at the same artifact URL. Personal data stays. An interrupted update keeps its target and recovery marker. Resume it at the same address. A hash mismatch, changed target, or incomplete data readback stops the update. Never clear a marker to hide a failure. Signed one-tap updates are not enabled.

## Read-only shares and turnover

A read-only share shows rank and last name, tier, relationship role, last session, next due, late flag, and the program document. It hides records, notes, targets' text, and mentoring. Share revocation and private-path isolation still require the separate account acceptance test before public release. Turnover uses a reviewed roster and program handoff into the relief's own notebook. Editor overlap is unverified; use the handoff.

## After a downgrade

Reading, exporting, and deleting an existing notebook after a downgrade from Pro are unverified until tested on a downgraded account. Do not rely on continued access. Preserve permitted exports before changing plans. Use Claude account support for plan and deletion questions.

## Adverse routing

The adverse card is available on every record. Advisory signals never decide that an offense occurred. Keep factual observations without findings. The notebook never drafts a 6105 entry or a page 11.

- Immediate safety: contact emergency services and the command's emergency channels.
- Suspected offense: stop questioning that could require a rights warning; route to the commanding officer with the SJA's advice. Defense counsel is a separate route from the command SJA.
- EO, IG, or SAPR matter: use the applicable protected channel. Keep protected communications out of the notebook.
- Formal personnel action: the commanding officer decides, supported by admin and the SJA. A 6105 entry has written deficiencies, available assistance, consequences, a reasonable opportunity to correct, and the commanding officer's signature. An ordinary page 11 is different. Confirm current procedures and rights with the responsible office.

## Report a problem

Use Report a problem from any notebook screen. Copy diagnostic works without Ask or saved records. Review version, pack, screen, capability states, and recent error classes. The diagnostic excludes personal values and stack traces. Leader's Notebook sends nothing automatically.

Review the text before you choose to email [feedback@warfarecommand.com](mailto:feedback@warfarecommand.com). Include the version, screen, what you tried, what happened, and a clean diagnostic if useful. Exclude names, service dates, notebook links, record text, and protected details. Report security issues privately to [security@warfarecommand.com](mailto:security@warfarecommand.com). Do not post a private record in a public issue.

## Export to GenAI.mil

The method packet contains cited rules, three Word and Markdown record templates, saved standing guidance, blank record and session schemas, synthetic examples including adverse routing, and verify/CHECKS.md with exact prompts and pass criteria. Records, notes, and mentoring stay out. Add a roster only on the second tap after reviewing the included fields. Review the complete file list before saving.

On the CAC side, go to DoD SAFE, log in, choose Send a drop-off request, enter the email address you will upload from, and send. On your personal device, open the request email, continue as a guest, upload the packet, and send. Retrieve the pickup on the CAC side and upload the files to GenAI.mil with PROMPT.txt.

Load the packet and use PROMPT.txt. Run verify/CHECKS.md to find out whether the receiving model can reuse the skill in a new session, keep the junior worksheet format, and route the adverse example. Test the other two formats and confirm sharing with another authorized person. The packet README explains sharing and updates. If persistence is unavailable, use the packet and prompt in each session. Persistence and sharing require the named model acceptance checks.

## Full reset

Automatic deletion of the entire saved notebook is unavailable because the page cannot bind a delete to a concurrent legal hold. Archive Marines to keep their entries. Use Delete records on an archived Marine's page only when you choose deletion. A retained legacy reset journal offers restoration of missing documents. Delete downloaded files separately.


## Current platform limits

Private page documents use `data/users/<uid>/ln/<kind>/<id>` and collections use `data/users/<uid>/ln/<kind>`, built from document and collection refs. Await `user.id()`. Document paths have an even segment count; collection paths have an odd count. Snapshots expose an `exists` boolean and `data()` returning a frozen body. Clone that body before editing. Owner controls require `user.canEdit()`; another viewer's private subtree remains invisible. Chat ArtifactData uses `data/users/me/ln/` for this same namespace.

Word exports read the Marine fresh and refuse a legal hold before generation and the save prompt. A successful save resolves `{status:"saved"}`; `{status:"delivered"}` means delivery to a requested destination, not a saved copy. A decline rejects with `declined` and does not retry. Archive is the default after closeout counseling. It keeps records, notes, targets, and mentoring, removes the Marine from active scheduling and shared status, and can be undone with Reactivate. Delete records is a separate later choice on the archived Marine page. After a saved Marine copy and your confirmation, deletion checks the hold and removes covered documents with readback. If a new hold appears, removal stops and lists exactly which documents were removed and which remain. A hold entered on another device during a save prompt or between a hold check and deletion can arrive too late to prevent that save or deletion. These are accepted residual risks; review holds before exporting or deleting records.

## Setup and record saves

The notebook shows setup steps while it saves your answers and verifies installation metadata. Keep the same page open; a paused setup can retry there. Your last name, first name, and middle initial belong on the first card and can be edited in Settings, Profile. New records prefill those fields in Section A.

Saving means a write is still pending. You can keep typing; changes made during that write remain marked Not saved until you save them. Word records use Counseling Last DDMONYYYY.docx. Delete records requires a new Marine copy if covered documents changed after the accepted copy.

## Archive a Marine

Choose Archive Marine on the Marine's page. Records stay in your notebook. You can reactivate any time. Depart and close out offers the closeout session, then Archive as the default end state. Neither action asks you to delete.

Deletion is your choice. On the archived Marine's page, Delete records opens its own sheet with the NAVMC 2795 para 3005.1.i rule, the Marine copy option, legal hold checks, and explicit confirmation. A legal hold blocks export and deletion; archiving keeps the held records. Mentoring is kept when counseling records are deleted.
