# OSS management

There instructions are about managing a collection of open source projects.
The source of truth on which projects we operate on is
<https://markkarpov.com/oss>. There, each header defines a group of projects
that the user will likely want to manipulate as a whole by applying a change
to every project in the group. The 3 first items in the MMark category
(MMark, MMark CLI, and MMark extensions) should also be recognized as
Haskell even though they are in their own section.

## Local checkouts

Every project in question has a local checkout. The root for all checkouts
from GitHub is at `~/projects/`. Then we append to that directory first the
organization or user name and then the name of the project. For example,
Megaparsec lives at `~/projects/mrkkrp/megaparsec`. If you asked to perform
an action on a group you first need to make sure that every project in that
group is available locally, that is to say: it is cloned, and its up to date
`master` is checked out. If you find that a different branch is checked out,
first switch to current `master`. If you find uncommitted changes, stash
them first.

## Making a change

When asked to perform a change that applies to a group, make that change on
the first project in the group and open a PR. Report the link to the PR to
the user for review. Work on the change with the user until it is approved
for mass-replication. Then, apply analogous changes to all projects in the
group (one PR per change) and present a table of projects/PR links to the
user. Double-check that all projects in the group are covered and none is
skipped. Arm a watch per PR and merge the changes once CI is green for each
respective PR. Report completion when all PRs have been merged and CI is
green on `master` for all of them. If any `master` is red, report that.
