# Assignment 2 - classification and evaluation (individual)

This assignment builds a logistic regression classifier and its evaluation machinery from
first principles, then puts both to work on a realistic decision: where to set the
threshold for a lending model.

## Task

Working in `starter.ipynb`, standard library only, you will implement `sigmoid`,
`log_loss`, `predict_proba`, `fit_logistic`, `confusion_counts`, `precision_recall_f1` and
`choose_threshold`. Each function builds on the last, so get the numerically stable
version of `sigmoid` and `log_loss` right early, since every later function depends on
them behaving sensibly near the extremes.

Once the model fits, the interesting part starts: a lending decision is not well served
by accuracy alone, and the assignment asks you to reason about the relative cost of a
false positive against a false negative, then choose and defend a threshold rather than
defaulting to 0.5. Treat the write-up as seriously as the code; a numerically correct
model with no defensible threshold is only half the assignment.

Suggested steps:

- Implement and unit-test `sigmoid` and `log_loss` before anything else.
- Build `fit_logistic` and check it converges on a toy dataset with a known answer.
- Implement `confusion_counts` and `precision_recall_f1`, and sanity-check them against a
  hand-worked example.
- Use `choose_threshold` to explore the precision-recall trade-off across the cost ratio
  the brief describes.
- Restart the kernel and run all cells before you commit.

## What to submit

Push your completed `starter.ipynb` to `main` - that push is your submission. Every
top-level cell must run cleanly, since the grader converts the notebook to a script and
imports it directly; a cell that raises stops the import and costs you every automated
mark.

## Grading

- Automated tests against the seven required functions.
- Code quality: clear names, no repetition, and the numerical guards the docstrings ask for.
- The written threshold justification: the cost ratio you chose, what it implies, and one
  thing this evaluation cannot settle.
