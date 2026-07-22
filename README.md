# AI 301: Open Source Contribution Progress Journal

**Project:** [skorch-dev/skorch](https://github.com/skorch-dev/skorch)
**My fork:** [Sweeyya/skorch](https://github.com/Sweeyya/skorch)
**Issue:** [skorch-dev/skorch #<issue-number>](https://github.com/skorch-dev/skorch/issues/<issue-number>): Dataset + stratified split fails with unclear error

Interest note: I'm aiming to work on something PyTorch focused for this course. skorch is a scikit learn style wrapper built directly on PyTorch, chosen for that reason after evaluating and ruling out several other candidates (see below).

## Phase I: Issue Selection ✅ Complete

* **Issue evaluated for fit:** Bug is reproducible with a minimal script (uses sklearn's built in breast cancer dataset, no GPU or external data needed). A maintainer (`@BenjaminBossan`) already responded to the original reporter and explicitly scoped down the accepted fix to two concrete deliverables, ruling out riskier approaches. This significantly de risks a first PR since the acceptable scope is maintainer confirmed rather than guessed.
* **In my own words:** skorch's docs say you can pass a PyTorch or skorch `Dataset` directly to `.fit()`. Doing so currently fails with a confusing error (`ValueError: Stratified CV requires explicitly passing a suitable y`), because the default validation split logic can't pull class labels out of a `Dataset` object the way it can from raw arrays. The fix (per the maintainer) is: (1) detect this case and give a clearer, actionable error message, and (2) add a docs or FAQ entry describing the workaround.
* **Comment posted:** Asked to take over from the original reporter (who proposed the fix but never opened a PR), restating the maintainer approved scope for confirmation. ✅ **Maintainer confirmed.** `@BenjaminBossan` cleared me to pick up the work, approving the error message and docs improvements and explicitly ruling out guessing `y` from the passed dataset.
* **GitHub setup:** ✅ Account confirmed, repo forked (`Sweeyya/skorch`), cloned locally, `upstream` remote added and verified via `git remote -v`.

**Note on process:** I initially considered `run-llama/llama_index` per the course's default walkthrough, but pivoted to free choice after confirming with the course that this was allowed, specifically to get PyTorch focused experience. Along the way I evaluated and ruled out several issues for legitimate reasons (already claimed, mismatched product surface, live unpatched security disclosures, an unmaintained project, a bot generated CI issue) before landing on this one.

## Phase II: Reproduce & Plan 🟨 In progress

**Confirmed scope (from maintainer):** improve the error message and add a docs or FAQ entry. Out of scope: guessing `y` or auto disabling stratification. The user stays explicit.

* [ ] `uv` or environment setup (need to confirm skorch's actual tooling, not necessarily `uv`)
* [ ] Package's test suite runs successfully as a baseline
* [ ] Bug reliably reproduced locally
* [ ] Plan written: root cause, fix approach, test plan

## Phase III: Build ⬜ Not started

## Phase IV: Submit & Iterate ⬜ Not started

***

*Last updated: July 21st*
