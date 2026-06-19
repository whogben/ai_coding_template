## AGENTS.md
This document contains all guidance for the project agents.
- Follow all rules in this document exactly.
- Multiple agents in different harnesses will share the project, so all development guidance and common procedures must be included here.
- Do not edit this `AGENTS.md` file without getting the user's explicit signoff on the exact wording of the changes.


## Design Document
`DESIGN.md` at the project root is the authoritative design document.

### Stop and read the design document now
There is no scenario where you can work on the project without reading the design document first - so read it now before continuing.

### Follow the design document exactly
You may never deviate from the design document *for any reason*.
- Design document mistakes: Stop and alert.
- Design document omissions: Stop and alert.
- Design document ambiguities: Stop and alert.

There is never a scenario where any part of the products' interface or behavior varies at all from what is described in the design document.

This means that changes to the design should not be committed separately from the code that implements those changes - each commit should have matching design and code.

### Document all design decisions before building
Anytime the user tells you to make a change, you must document the decision in the design document.

Example: A fully defined request - change the document and get it done.
> User: The button title should say 'Hello'.
> Assistant: OK, changing design document, then changing code.

Example: An open-ended request - confirm the specific design changes before continuing.
> User: The button title should be a greeting.
> Assistant: OK, how about I change the design to: `The hero banner button is titled 'Hello'`

Example: A hypothetical or exploratory request - consider it without making changes.
> User: What about a feature where the button changes color when hovered over?
> Assistant: We could add `hilights <color> on hover` to the design document, and then change some CSS.

Example: A request that is not a design decision - just get it done.
> User: The button isn't working.
> Assistant: OK, investigating and fixing.


## Project Layout
The files and folders in the project are organized as follows:
```
AGENTS.md               # these project rules
DESIGN.md               # authoritative design document
README.md               # project description and usage instructions
CHANGELOG.md            # changelog
scripts/                # project scripts
    build.py            # builds the product(s)
    test.py             # tests the built product(s)
    publish.py          # publishes the built product(s)
```

### Update and maintain the project layout
As you make changes to the project, ensure the project layout is accurate and up to date with the meaningful files and folders in the project.

Example: You see a new file in the project - add it to the layout.
> Assistant: I see a file that isn't in the layout - let me read it to understand what it is, and then update `AGENTS.md` project to reference it.

Example: You see a file that is no longer in the project - remove it from the layout.
> Assistant: I see a file that is no longer in the project - let me remove it from the project layout.

Example: You change the meaning and use of a file - update the layout.
> Assistant: Now that this file is primarily devoted to testing, let me update the note in the project layout ot reflect that.


## Git repo
This project is based in a git repository and may have multiple developers working on it in parallel.

### Pull the latest changes from the remote repository
Before you start working on the project, pull the latest changes from the remote repository to your local repository.

> User: Lets get to work, add a button that ...
> Assistant: OK, let me pull the latest changes first...

### Commit and push your changes when complete and tested
After you have made changes and tested them, commit your changes to the local repository and then push them to the remote repository.

### Commit message format
All commit messages follow the same format: `(type): description of the changes` where type might be:
- feat: new feature
- fix: bug fix
- etc, whatever is appropriate for the changes.


## README
Keep a README file at the root of the project describing the project, its purpose, and how to use it.

### Keep the README up to date when making changes
Every change that impacts a user could potentially impact the README, so consider it when making changes.

Example: You add a new feature - add to the README.
> Assistant: Now that I've added the feature, let me update the README so users know about it.

Example: You change a behavior - check README for consistency.
> Assistant: The user-facing behavior has changed - let me confirm if the README references the old version or needs edits.  

Example: The project has drifted a long way from the README - raise it to the user.
> Assistant: The README frames the project as being about X, but most of the functionality is now Y - let me consider if a refactor would improve it and suggest it to the user.


## CHANGELOG
Keep a changelog in the `CHANGELOG.md` file at the root of the project following Keep a Changelog (KCL) format.
- Prior to version 1.0, we use a custom version numbering system: `0.<major>.<minor>`.\
- Accumulate changes under the `[Unreleased]` section.
- When the user requests to release, suggest the version bump to the user and get confirmation before proceeding.