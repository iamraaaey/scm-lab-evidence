# Session 2 Reflection

## Q1. How do Issues and pull requests together support change control?

Issue #1 recorded why the change was needed and what "done" meant, through its context and two acceptance criteria. Pull request #2 carried the actual change from the branch issue-1-traceability-template and gave a place to review it before it reached main. Writing "Closes #1" in the pull request description linked the two, so GitHub closed the issue automatically when the pull request was merged. Anyone reading the history later can follow the chain from the reason (#1) to the reviewed change (#2) to the merge commit eaa7ae9.

## Q2. Why did the conflict in Part 4 happen, and how could a team reduce such conflicts?

branch-a and branch-b were both created from the same commit on main (ee9464e), and each changed the same line of session2/conflict-demo.md to a different value: staging and production. Merging branch-a into main was clean, but when branch-b was merged after it, Git could not decide which version of the line was correct, so it stopped and asked a person to choose. A team can reduce such conflicts by keeping branches small and short-lived, pulling main often, and avoiding two people editing the same lines at the same time. Decisions such as the deployment target can also be agreed in an Issue first, so only one branch needs to change that line.

## Q3. What would be lost if people merged straight into main without a pull request?

Without a pull request there is no point where someone checks the change against the acceptance criteria before it reaches main. The discussion would also be lost: the review comment on PR #2 about recording the merge date would have nowhere to live. The link between the change and its reason would disappear too, because there would be no "Closes #1" to connect the work to Issue #1, so the issue would not close automatically and the traceability note would have no pull request or review to point to. Mistakes would then reach main more easily, and they would be harder to trace back later.
