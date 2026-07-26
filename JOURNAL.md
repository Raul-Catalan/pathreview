## Week 7 — Issue selection

**Issue link:** [https://github.com/ascherj/pathreview/issues/153]

**Issue title:** [Faithfulness checker crashes when a context chunk has
`text: None` #153]

**Tier:** [x] Tier 1 [ ] Tier 2 [ ] Tier 3

**Problem summary:** [The FaithfulnessChecker is crashing when we feed the
Checker `[{'text': None}]`. This is happening because the FaithfulnessChecker is
not able to detected when 'text' is None and when following `join` is called on
the none object, it results in a TypeError being raised. A successful fix is
correctly catching when None context is passed to the faithfulness checker and
catching the TypeError and passing an empty string to the Faithfulness checker.]

**Branch name:** [fix/153-fix-faithfulness-checker-crashes]

**Setup confirmation:** [x] App runs locally at localhost:5173

**Cohort ledger:** [x] Issue added to cohort ledger

## Week 8 — Reproduction & solution planning

**Reproduction commit link:**
[https://github.com/ascherj/pathreview/commit/3c8db6d2e067f741f53753b6be2df4983b317092]

**Reproduction summary:** [To reproduce the issue we can run
`pytest tests/unit/test_faithfulness_checker.py::TestFaithfulnessChecker::test_none_context_chunk_text`.]

**PLAN.md link:**
[https://github.com/Raul-Catalan/pathreview/blob/fix/153-fix-faithfulness-checker-crashes/PLAN.md]

**Walkthrough video (recommended):** []

**Blockers or open questions:** []

## Week 9 — Solution building & PR submission

### Check-in 1 (mid-week)

**Current progress:** [I have implemented the fix to stop the function from
throwing a TypeError when text = None. I have verified this works by running the
test cases against that scenario.]

**Next steps:** [The rest of the week Ill working on running `make check` and
preparing my PR.]

**Blockers:** []

---

### Check-in 2 (end of week)

**PR link:** [https://github.com/ascherj/pathreview/pull/300]

**Branch:** [153-fix-faithfulness-checker-crashes]

**What you built:** [I added a fix to a TypeError, by adding a fallback
statement if that were to fail. This allows the `check` method to run as
expected and passes the unit test cases.]

**Tests added or updated:** [No Tests where updated or added, only existing ones
passed]

**Self-review confirmation:** [x] make check passes [x] make test-unit passes

**Draft PR feedback received from:** [none]
