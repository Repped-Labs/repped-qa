# QA Intern Workflow

This is how QA works on this project. Read this before you touch anything.

---

## What you're testing

You are blackbox testing widgets embedded inside a **Circle community** on a staging environment. You test as a real logged-in Circle member — you have no access to the source code, no access to the private codebase, and no access to production.

Everything you find goes into a GitHub Issue in **this repo** using the Bug Report template.
Everything you need to test is a GitHub Issue in **this repo** using the QA Task template.

---

## Access you need

| Thing | How you get it |
|---|---|
| This GitHub repo | You're already here — it's public |
| Staging Circle community | Trinity gives you the invite link |
| Your Circle login | Use the account Trinity set up for you |

You do not need — and will not get — access to the private codebase. Blackbox means blackbox.

---

## What "testing in Circle" means

Widgets are embedded directly inside Circle posts and spaces as iframes. You test them the way a real member would use them — inside Circle, logged in, as yourself.

**This means you are testing:**
- The widget loading inside a Circle post (the spinner, then the widget appearing)
- The full widget UX as an actual Circle member
- Whether your identity is recognized (your Circle account is your test account)
- Behavior across page reloads, tab switches, and browser restarts
- How the widget behaves at different screen sizes inside Circle's layout

**You are NOT testing:**
- The raw Vercel URL directly (unless a QA task specifically asks you to)
- Anything behind the codebase — you cannot see it and should not try to access it
- Production — always use the staging community Trinity links you to

---

## The board

Go to the **GitHub Project board** linked in the repo. This is your home base.

**Columns:**

| Column | What it means |
|---|---|
| **Ready for QA** | Unclaimed tasks. Pick one up. |
| **In QA** | You're actively testing this. |
| **Needs Fix** | You found bugs. Waiting on Trinity. |
| **QA Passed** | Tested and signed off. Done. |

**Views to use:**

- **Unassigned** — tasks with no assignee. These are up for grabs.
- **Mine** — tasks assigned to you. Your current work.
- **Stale** — items with the `stale` label. Sitting 3+ days untouched. Clear these first.

---

## How to pick up a task

1. Go to the board → **Ready for QA** column
2. Start with `priority: high` items, then unassigned ones
3. Open the issue, read everything — especially **Out of scope**
4. Assign yourself to the issue
5. Change the label to `status: in qa` — it moves to the In QA column automatically
6. Go to the staging Circle community and test

**One task at a time.** Finish what you pick up before grabbing another.

---

## How to test

You are doing **blackbox testing**. That means:

- Test from a real user's perspective only
- Log into the staging Circle community with your Circle account
- Navigate to the post or space Trinity linked in the QA task
- Go beyond the listed areas — the task gives you a starting point, not an exhaustive list

**Things that are always worth trying, regardless of the task:**
- Reload the page mid-action — does state persist?
- Open in a second browser tab — do both stay in sync?
- Try on a different browser (Chrome vs Firefox vs Safari)
- Resize the window — does anything break at smaller sizes?
- Move fast — click things before they finish loading
- Try empty inputs, very long inputs, special characters

**Treehouse stages that unlock each level of QA work:**

| Your sprint | Treehouse content | What it enables |
|---|---|---|
| Sprint 1 | Stage 1 (Why We Test) + Stage 4 (Bug Reporting) | Filing accurate bug reports |
| Sprint 2 | Stage 2 (Test Cases) + Stage 3 (Executing Tests) | Writing test cases before testing, structured execution |
| Sprint 3+ | Stage 5 (Beyond Testing Basics) | Regression testing, exploration charters |

---

## How to file a bug

Use the **Bug Report** issue template. Every field is required — incomplete reports get sent back.

**Title format:** `[BUG] Short description of what's broken`

**Link every bug to its QA task** — in the bug report body, write `Relates to #[QA task number]`.

**One issue per bug.** Never combine multiple bugs into one report.

**Severity — use your Treehouse definitions:**

| Severity | Meaning |
|---|---|
| **Critical** | Core feature completely broken. No workaround. |
| **High** | Major feature broken. Workaround is painful. |
| **Medium** | Feature partially broken. Reasonable workaround exists. |
| **Low** | Minor — cosmetic, edge case, slight inconvenience. |

When in doubt, go one level higher. Easier to downgrade than miss a real problem.

---

## How to close a task

When you finish testing — pass or fail — close the QA task with a comment.

**If everything passed:**
```
QA passed. Tested in Circle staging on Chrome 124 / macOS.

Checked:
- Task completion persists on reload ✓
- Notes save correctly ✓
- Theme sticks across sessions ✓
- Works in Firefox too ✓

No issues found. Good to ship.
```

Move to **QA Passed**. Change label to `status: qa passed`.

**If you found bugs:**
```
QA failed. Found 2 issues:

- #47 — task checkbox resets on reload (High)
- #48 — custom accent color lost after 10 min (Medium)

#47 is a blocker. Should not ship until fixed.
```

Move to **Needs Fix**. Change label to `status: qa failed`.
Trinity fixes → re-opens the task → you re-test the fixed areas.

---

## Rules

- **One task at a time.**
- **Never close a task without a comment.** Explain what you tested and what you found.
- **Every bug = its own issue.** No combining.
- **Stale items = priority.** If something has the `stale` label, it's been waiting — clear it.
- **Never test on production.** Staging only. The link is in each QA task.
- **Ask before skipping.** If a task is unclear, comment and ask Trinity rather than skipping it.
