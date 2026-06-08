# QA Apprentice Workflow

This is how QA works on this project. Read this before you touch anything.

---

## What you're testing

You are blackbox testing widgets embedded inside a **Circle community**. You test as a real logged-in Circle member — you have no access to the source code, no access to the private codebase, and no access to production.

Everything you find goes into a GitHub Issue in **this repo** using the Bug Report template.
Everything you need to test is a GitHub Issue in **this repo** using the QA Task template.

---

## Access you need

| Thing | How you get it |
|---|---|
| This GitHub repo | You're already here — it's public |
| QA community | Trinity gives you the invite link |
| Your Circle login | Use the account Trinity set up for you |

You do not need — and will not get — access to the private codebase. Blackbox means blackbox.

---

## The board

Go to the **[QA Board](https://github.com/orgs/Repped-Labs/projects/7)**. This is your home base.

Every task on the board is open. Pick up anything in **Ready for QA** — there is no sprint gating, no level requirement. If it's on the board, you can test it.

**Columns:**

| Column | What it means |
|---|---|
| **Ready for QA** | Unclaimed — pick it up |
| **In QA** | You're actively testing this |
| **Needs Fix** | You found bugs. Waiting on Trinity. |
| **QA Passed** | Tested and signed off. Done. |

---

## How to pick up a task

1. Go to the board → **Ready for QA** column
2. Start with `priority: high` items first, then anything unassigned
3. Open the issue, read the full description and **Out of scope** section
4. Assign yourself
5. Change the label to `status: in qa` — it moves columns automatically
6. Open the QA community and start testing

**One task at a time.** Finish what you pick up before grabbing another.

---

## How to test

You are doing **blackbox testing**:

- Test from a real user's perspective only — you see what a real member sees
- Log into the QA community with your Circle account
- Navigate to the Circle post or space linked in the QA task
- The test areas in the issue are a starting point — go further

**Always worth trying on any task:**
- Reload the page mid-action — does state persist?
- Open the same page in a second browser tab — do both stay in sync?
- Try a different browser (Chrome, Firefox, Safari)
- Resize the window — does anything break at smaller sizes?
- Move fast — click things before they finish loading
- Try empty inputs, very long inputs, special characters

---

## How to file a bug

Use the **Bug Report** issue template. Every field is required — incomplete reports get sent back.

**Loom is required for every bug.** Record your screen showing the bug happening. Paste the Loom link in the Screenshot field. No Loom = report gets sent back.

**Title format:** Start with the feature, not "It" or "The". Example — "Task checkbox does not persist after reload."

**Link every bug to its QA task** — write `Relates to #[issue number]` in the report.

**One issue per bug.** Never combine multiple bugs into one report.

**Severity:**

| Level | Meaning |
|---|---|
| **Critical** | Core feature completely broken. No workaround. |
| **High** | Major feature broken. Workaround is painful. |
| **Medium** | Feature works but behaves incorrectly. Workaround exists. |
| **Low** | Minor — cosmetic, edge case, slight inconvenience. |

When in doubt, go one level higher.

---

## How to close a task

Always close with a comment — pass or fail.

**If everything passed:**
```
QA passed. Tested on Chrome 124 / macOS in the QA community.

Checked:
- Task completion persists on reload ✓
- Notes save correctly ✓
- Theme sticks across sessions ✓
- Tested on Firefox too ✓

No issues found.
```

Change label to `status: qa passed`.

**If you found bugs:**
```
QA failed. Found 2 issues:

- #47 — task checkbox resets on reload (High) [Loom: loom.com/...]
- #48 — accent color lost after 10 min (Medium) [Loom: loom.com/...]

#47 is a blocker.
```

Change label to `status: qa failed`. Trinity fixes → task reopens → you re-test.

---

## Rules

- **Pick up anything on the board.** No gating, no prerequisites.
- **Loom every bug.** No exceptions. No Loom = report sent back.
- **One task at a time.**
- **One bug = one issue.** Never combine.
- **Never close without a comment.**
- **Never test on production.** QA community only — the link is in the task.
- **Stale items = priority.** `stale` label means it's been waiting 3+ days — clear it first.
- **Ask before skipping.** Comment on the issue and tag Trinity.
