# Approach

## Issues

We use GitHub Projects for managing work.
Projects have issues which have a numeric ID, title and description.
The `ISSUE-ID` and title are used to create a short lived branch for the work.
The description is used to capture the requirements for the work.
Projects have a Kanban board which is used to track the release of the work.

## Code

The development approach emphasises Continuous Delivery and Continuous Integration.
Work is done on branches with the following naming convention, see `https://www.conventionalcommits.org/`:

- `chore/ISSUE-ID/Description`
- `feat/ISSUE-ID/Description`
- `fix/ISSUE-ID/Description`
- `hotfix/ISSUE-ID/Description`

Note that `ISSUE-ID` should link back to a GitHub Project Board (see above) which captures the requirements and tracks the release of the
work.
These branches are deleted once merged to the main branch.
