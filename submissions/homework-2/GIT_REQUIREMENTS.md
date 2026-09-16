# Homework 2 — Part 2 Submission

assignments/homework-2/GIT_REQUIREMENTS_TEMPLATE.md

Student name: Jianhua Liu

GitHub username: Monsterfat

## 1. Git Command Observations

| Command or workflow | What did you observe? | What was the user trying to accomplish? | What problem or risk did it address? |
|---|---|---|---|
| 1. Git status| a file marked in red  | Trying to see if the repo is fine as is or there is an issue that needs to be addressed | Basic information gathering  |

| 2. Git diff –staged | Added and removed lines from the file  | Observing what was removed and what was added during the editing of the file  | looking at what’s need to be reviewed before moving on with the staging  |

| 3. Git add <file>| successfully added without error message  | User trying to complete the staging area and trying to move on to the commit by accepting all the changes that was made  | Addresses the issue of changes still within the staging area  |

| 4. Git commit -m “(_____)”| Committing on the changed file  | User is trying to communicate what was changed to the other contributors  | It solves an otherwise unknown change for everyone involved working on something that might’ve already been finished |


## 2. User Needs

### UN-GIT-01 — Short descriptive title

> UN-GIT-01 – A Editor needs a way to Identify a problem because of unclear information given by previous editors

### UN-GIT-02 — Short descriptive title

> UN-GIT-02 – A Author needs a way to Identify a change because due to previous editors having to correct parts of the file

### UN-GIT-03 — Short descriptive title

> UN-GIT-03 – A Editor needs a way to inform contributors because Someone working on a previous repo may already be working on the same file someone else is currently working on

## 3. User Requirements

| ID and short title | User requirement | Source user need | Rationale |
|---|---|---|---|
| UR-GIT-01 | UN-GIT-01: A contributor shall be able to edit sub-branches off the main if needed | UN-GIT-02 | Necessary to completing a task |

| UR-GIT-02 | UN-GIT-02: A Author shall be able to see all changes made | UN-GIT-01  | Knowledge of such is important |

| UR-GIT-03 | UN-GIT-03: A contributor shall be able to continue where the previous contributor left off at | UN-GIT-01 | Working for extended periods of time |

| UR-GIT-04 | UN-GIT-04: A contributor shall be able to push the project to repository if all changes are approved by others | UN-GIT-02 | Uploading for snapshot |

