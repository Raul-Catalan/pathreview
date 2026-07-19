## Week 7 — Issue selection

**Issue link:** [https://github.com/ascherj/pathreview/issues/153]

**Issue title:** [Faithfulness checker crashes when a context chunk has
`text: None` #153]

**Tier:** [x] Tier 1 [ ] Tier 2 [ ] Tier 3

**Problem summary:** [ The FaithfulnessChecker is crashing when we feed the
Checker `[{'text': None}]`. This is happening because the FaithfulnessChecker is
not able to detected when 'text' is None in this `if` statement:

```python
if not feedback or not context_chunks:
            logger.info("faithfulness_empty_input", has_feedback=bool(feedback),
                       has_chunks=bool(context_chunks))
            return 0.0
```

In the file `rag/evaluator/faithfulness_checker.py`, the `if` statement in the
object FaithfulnessChecker should catch if the text context is empty, however it
fails to do so and then when following `join` is called on the none object, it
results in a TypeError being raised. A successful fix is correctly catching when
None context is passed to the faithfulness checker. I think adding a recursive
check if the `"text"` keys' value is None will catch this error.]

**Branch name:** [fix/153-fix-faithfulness-checker-crashes]

**Setup confirmation:** [x] App runs locally at localhost:5173

**Cohort ledger:** [x] Issue added to cohort ledger
