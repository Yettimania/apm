# apm

> Agile project management from the command line.

'apm' is a Minimal Viable Program focused on a hierarchy of parents, children and tasks. It is a simple means of managing a project from the command line in place of flash cards, sticky notes, etc. 

It is generalized to a **parent** & **child** system so hierarchy can be defined by individual users. For example, **parents** may be defined as capabilites or features. Each **parent**, can have multiple children, or stories and each **child** can have multiple tasks associated with it. 

## Install

Utilizes fzf for search and browse capability.

Copy the file into a $PATH so 'apm' can be executed within any folder.'

'''sh
wget https://raw.githubusercontent.com/Yettimania/apm/master/apm
'''

'cd' into $PATH and make apm file executable with 'chmod +x apm' 

## Usage

'''sh
# Create a parent file.
$ apm [ -p PARENT ] 

# Create a child for a specified parent.
$ apm [ -c CHILD ] [ PARENT ]

# Create a task for a specified child.
$ apm [ -t TASK ] [ CHILD ]

# Search all files in a given directory for keyword
$ apm [ -s SEARCH ] [ KEYWORD ] 

# Launch fzf to browse all files in a given directory
$ apm [ -b BROWSE ]

# Update Status, Iteration or Assigneed for a list of files entered
$ apm [ -u UPDATE ] [ARGS]
$ i.e. apm -u 1.1,1.2,2.1

# Generate a iteration report and display parent, child and task files that are incomplete. Creates a CFM file for each iteration that can be used to generate CFM charts in prefered application.'
# apm [ -r REPORT ]
'''

The report output would appear as

'''sh
-------------------
ITERATION 1 SUMMARY
-------------------
Stories in Iteration: 2
Open Stories: 0
Closed Stories: 2

---Tasks Assigned to Stories---
3 tasks for 1.1
1 tasks for 1.2
---Task Summary for Iteration---
4 Total Tasks
      1 Todo
      1 Done
      2 Do
-------------------
ITERATION 2 SUMMARY
-------------------
Stories in Iteration: 1
Open Stories: 1
Closed Stories: 0

---Tasks Assigned to Stories---
2 tasks for 2.1
---Task Summary for Iteration---
2 Total Tasks
      1 Do
      1 Todo

----------------
Incomplete Cards
----------------
---No assigned Iteration---
---No assigned Status---
---No Assignee---
2.1.2
1.1.2
1.1.3
2.1.1
'''

For each iteration, a cumulative flow table counts the cumaltive 'Todo', 'Do' and 'Done' tasks for each iteration. This file can be used to review or plot the progress of the iteration.

![cfm.png]()

