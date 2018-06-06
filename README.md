# 132-494-F18C-500
Pocket Checklist - F/A-18C Hornet

[![Build Status](https://travis-ci.org/jkhoel/132-494-F18C-500.png?branch=master)](https://travis-ci.org/jkhoel/132-494-F18C-500)

## Notes:
Requires XeLaTex for typesetting!

## Re-use as template
This TeX project and git-setup is designet to be easily modified/expanded or used as template for other airframes.

### ChecklistSetup.tex
Adjusts formatting to better suit checklists, and also declares commands for use in defining checklist sections, subsections, checklist items and comments.

### NormalProcedures.tex
Use this file as a template for creating new checklists. Should be prety self explanatory when comparing to the typeset PDF.

## How to contribute
Each chapter is split out to seperate TeX files, like ChecklistSetup.tex and NormalProcedures.tex mentioned above, and each file has a seperate branch for editing and tracking changes to that spessific part of the document. Before editing anything, you need to checkout the correct branch.

### Checking out a branch
Example: Editing NormalProcedures.tex

```git
git checkout normal-procedures
```

* DO NOT EDIT ANY OTHER DOCUENTS ON THE BRANCH THEN THE ONE YOU CHECKED OUT *


### Creating a new document and branch
Example: Adding a new document called EmergencyProcedures.tex

```git
git checkout -b emergency-procedures && git push --set-upstream origin emergency-procedures
```

Note how the camel-cased TeX file translates into the branch name. Next step is to make the actual file and do commits as normal and finally, you need to check out the main document...
```git
git checkout main
```

... and add your new document to it:

```tex
 \input{./EmergencyProcedure.tex}
 ```

 Note the "./" before the file name. You need to provide UNIX style paths for all files and figures to include - or else the build process will fail.


