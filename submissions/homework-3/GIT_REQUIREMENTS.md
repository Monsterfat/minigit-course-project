## Approved UN/UR Baseline

ID
Stakeholder need

UN-GIT-01
A student developer needs a way to start tracking a local project because it has no recorded history.

UN-GIT-02
A student developer needs to know which project files have changed because they may forget what they edited before recording a checkpoint.

UN-GIT-03
A student developer needs to inspect changed content before recording it because a file may contain unintended edits.

UN-GIT-04
A student developer needs to choose the file content to include in the next checkpoint because some current changes may still be unfinished.

UN-GIT-05
A student developer needs to record a meaningful checkpoint because they want to record an important project version and provide a descriptive label.

UN-GIT-06
A student developer needs to review earlier checkpoints because they want to understand how the project reached its current state.

UN-GIT-07
A student developer needs invalid commands to explain why they failed while preserving existing project files and recorded checkpoints.


ID
User-visible capability
Need

UR-GIT-01
A student developer shall be able to initialize tracking in the current local project folder without removing existing project files.
UN-GIT-01, UN-GIT-07

UR-GIT-02
A student developer shall be able to see whether project files are untracked, staged, changed after staging, modified, deleted, or clean.
UN-GIT-02

UR-GIT-03
A student developer shall be able to view differences between current working file content and the content selected for the next checkpoint.
UN-GIT-03

UR-GIT-04
A student developer shall be able to view differences between content selected for the next checkpoint and the latest recorded checkpoint.
UN-GIT-03

UR-GIT-05
A student developer shall be able to select the current content of one existing project file for the next checkpoint without selecting unrelated files.
UN-GIT-04

UR-GIT-06
A student developer shall be able to create a checkpoint of selected content with a nonempty explanation while leaving later unselected edits in the working files.
UN-GIT-05, UN-GIT-04

UR-GIT-07
A student developer shall be able to view recorded checkpoints from newest to oldest, including their identifier and explanation.
UN-GIT-06

UR-GIT-08
A student developer shall receive a useful error when a command is invalid, a requested file is unavailable, or a path is outside the allowed project files.
UN-GIT-07

UR-GIT-09
A student developer shall be able to retry an operation after a failure without losing ordinary project files or an already recorded checkpoint.
UN-GIT-07


## Functional System Requirements

#SR-01 first init

SR-01 UR-GIT-01: Given no recorded history, when git init, MiniGit shall create a repository using the given files

#SR-02 repeated init

SR-02 UR-GIT-01/UR-GIT-08: Given a recorded history, when git init, MiniGit shall report back on a user error explaining that there is already a created repository

#SR-03 add one existing file

SR-03 UR-GIT-05: Given a target file folder containing multiple edited files, when git add<folder> is executed, MiniGit shall stage the one target file in the directory tree without affecting the other files in a directory.

#SR-04 add a missing file

SR-04 UR-GIT-08/UR-GIT-09: Given a file path that is outside the local project directory, when git add, MiniGit shall reject the command and output an error, while leaving the project state untouched

#SR-05 status for one staged file / status

SR-05 UR-GIT-03: Given status for staged file, when git status is used, MiniGit shall return with only one file in the staging area ready to be recorded for the next checkpoint while leaving the unmarked files out

SR-05A (single file): Given an existing edited project file, when git status is executed, MiniGit shall display its status without listing unrelated project files

SR-05B (excluding unrelated files): Given multiple edited filesi n the directory, when git status is run with a specific file, MiniGit shall isolate that speficic file and report on it

SR-05C (Target file validity): Given a file path, when git status is ran, MiniGit shall check if the path is valid and return an error if it cannot find the path

SR-05D (Editing staged file): Given a staged file has been deleted from working directory, when git status is executed, MiniGit shall report the file as missing or deleted without modifying the staging area

SR-05E (Checkpoint): Given a file in the staging area, when git status, MiniGit shall report a clear message as to what file is in the staging area that is queued for the next checkpoint

#SR-06 add single file

SR-06 UR-GIT-05: Given an existing project file (temp).txt, when git add (temp).txt, MiniGit will copy the entire content of (temp).txt into the staging area without staging any other file

#SR-07 create checkpoint

SR-07 UR-GIT-06: given staged changes, when git commit -m "__", Minigit shall create a snapshot commit with object ID, timestamp, and message

#SR-08 preserving un-staged

SR-08 UR-GIT-04/UR-GIT-06: Given staged changes grouped with un-staged edits, when git commit -m "__", MiniGit shall not clear or include the un-staged edits in the snapshot, untouched in the working tree

#SR-09 commit empty message error

SR-09 UR-GIT-06/UR-GIT-08: Given staged changes, when git commit -m "__", MiniGit must reject checkpoint creating and output an error stating that it cannot create a empty explanation

#SR-10 log history

SR-10 UR-GIT-07: Given recorded checkpoints, when git log, MiniGit shall print all commits in order from newest down to the oldest, displaying their id, timestamp, and message

#SR-11 add missing file error

SR-11 UR-GIT-08: Given a non-existent file path (missing.txt), when git add missing.txt, MiniGit shall display an error message stating that the file does not exist or outside project folder

#SR-12 state recovery after error

SR-12 UR-GIT-08/UR-GIT-09: Given an invalid command or missing file path, MiniGit will maintain its current state of all files, staged contents, and committed snapshots to be retried immediately

