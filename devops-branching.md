Branching + Development
-----------------------

- Keep it as simple as possible
- A single main branch + topic branches (short-lived!)
- Write tests for every single feature + every bugfix
- Use feature toggles to control feature releases (not branches!)

> Use branching to ensure only working code is merged into your main branch. Don't use it to control feature releases.

```plantuml
@startuml
title Branching

[*] --> Branch : Topic branch\n(off master)
Branch : git checkout -b ...
Branch : feature/*
Branch : bugfix/*
Branch : docs/*
Branch : translations/*

Branch --> Changes : Developer\nwrites code
Changes : git add -v .
Changes : git commit -m ...
Changes : git push -u origin ...

Changes -> MergeRequest : Create or\nupdate MR
MergeRequest : MR description: Change log
MergeRequest : Checks & tests run automatically
MergeRequest : Review app is deployed

MergeRequest -> MergeRequest : Static\ncode\nanalysis
MergeRequest -> MergeRequest : Unit\ntests
MergeRequest -> MergeRequest : Code review\ncomments
MergeRequest -> MergeRequest : Manually verify\nreview app
MergeRequest --> Changes : Incorporate\nreview\nfeedback

MergeRequest --> [*] : Merge changes,\ndelete topic branch

@enduml
```
