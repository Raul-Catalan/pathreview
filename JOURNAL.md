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

**Bug Reproduction Steps:** [To reliably reproduce the issue: running
`pytest tests/unit/test_faithfulness_checker.py::TestFaithfulnessChecker::test_none_context_chunk_text`
produces the failing test case]
