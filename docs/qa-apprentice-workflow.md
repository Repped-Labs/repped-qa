# QA Apprentice Workflow

This is how QA works on this project. Read this before you touch anything.

---

## What you're testing

You are blackbox testing widgets embedded inside a **Circle community**. You test as a real logged-in Circle member — you have no access to the source code, no access to the private codebase, and no access to production.

Everything you find goes into a **comment on the QA task issue** and a separate **Bug Report issue** for each bug.

---

## Access you need

| Thing | How you get it |
|---|---|
| This GitHub repo | You're already here — it's public |
| QA community | [qa.reppedlabs.org](https://qa.reppedlabs.org/feed) |
| Your Circle login | Use the account Trinity set up for you |

You do not need — and will not get — access to the private codebase. Blackbox means blackbox.

---

## The board

Go to the **[QA Board](https://github.com/orgs/Repped-Labs/projects/7)**. This is your home base.

Every task on the board is open. Pick up anything in **Ready for QA** — no gating, no prerequisites.

**Columns:**

| Column | What it means |
|---|---|
| **Ready for QA** | Unclaimed — pick it up |
| **In QA** | Actively being tested |
| **Needs Fix** | Bugs found — Trinity is on it |
| **QA Passed** | Signed off and done |

Trinity manages column moves and closing. Your job is to test and report.

---

## How to pick up a task

1. Go to the board → **Ready for QA** column
2. Start with `priority: high` items first
3. Open the issue, read the full description and **Out of scope** section
4. Assign yourself
5. Change the label to `status: in qa`
6. Go to [qa.reppedlabs.org](https://qa.reppedlabs.org/feed) and test

**One task at a time.** Finish what you pick up before grabbing another.

---

## How to test

You are doing **blackbox testing** — you see exactly what a real member sees. Nothing more.

- Log into the QA community at [qa.reppedlabs.org](https://qa.reppedlabs.org/feed)
- Navigate to the Circle post or space linked in the QA task
- The test areas listed are a starting point — go further

**Always worth trying on any task:**
- Reload the page mid-action — does state persist?
- Open the same page in a second browser tab — do both stay in sync?
- Try a different browser (Chrome, Firefox, Safari)
- Resize the window — does anything break at smaller sizes?
- Move fast — click things before they finish loading
- Try empty inputs, very long inputs, special characters

---

## How to report your findings

When you finish testing a task — or hit a natural stopping point — **add a comment on the issue**. Do not close it. Trinity reviews your comment and handles next steps.

**If you found no issues:**
```
Tested on Chrome 124 / macOS in the QA community.

Checked:
- Task completion persists on reload ✓
- Notes save correctly ✓
- Theme sticks across sessions ✓
- Tested on Firefox too ✓

Nothing found.
```

**If you found bugs:**
```
Found 2 issues — filed separately:

- #47 — task checkbox resets on reload (High)
- #48 — accent color lost after 10 min (Medium)

Loom of both: loom.com/...
```

That's it. Add the comment, leave the issue open. Trinity takes it from there.

---

## How to file a bug

Every bug gets its own GitHub Issue using the **Bug Report** template.

**Loom is required for every bug.** Record your screen showing the bug happening. Paste the link. No Loom = report gets sent back.

**Title:** Start with the feature, not "It" or "The."
Example — "Task checkbox does not persist after reload."

**Link it back:** Write `Relates to #[QA task number]` in the report.

**One issue per bug.** Never combine.

**Severity:**

| Level | Meaning |
|---|---|
| **Critical** | Core feature completely broken. No workaround. |
| **High** | Major feature broken. Workaround is painful. |
| **Medium** | Feature works but behaves incorrectly. Workaround exists. |
| **Low** | Minor — cosmetic, edge case, slight inconvenience. |

When in doubt, go one level higher.

---

## Rules

- **Pick up anything on the board.** No gating, no prerequisites.
- **Loom every bug.** No exceptions. No Loom = report sent back.
- **One task at a time.**
- **One bug = one issue.** Never combine.
- **Comment, don't close.** Trinity handles closing and status.
- **Never test on production.** QA community only — [qa.reppedlabs.org](https://qa.reppedlabs.org/feed)
- **Stale items = priority.** `stale` label means it's been waiting 3+ days — clear it first.
- **Ask before skipping.** Comment on the issue and tag Trinity.
