Branching + Development
=======================

- Keep it as simple as possible
- A single main branch + topic branches (short-lived!)
- Write tests for every single feature + every bugfix
- Use feature toggles to control feature releases (not branches!)

> Use branching to ensure only working code is merged into your main branch. Don't use it to control feature releases.

```plantuml
@startuml
title Branching

[*] --> [*]: master

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

Changes --> mr : Create or\nupdate MR
mr : MR description as Change log

state "Merge Request" as mr {
  state "Static\ncode\nanalysis" as checks
  state "Unit\ntests" as tests
  state "Review\napp" as reviewapp

  checks -> tests
  tests -> reviewapp

  state "Code\nreview" as codereview
}

mr --> Changes : Incorporate\nreview\nfeedback

mr --> [*] : Merge changes,\ndelete topic branch

@enduml
```

Related Topics
--------------

- [Build images](devops-environments.md) ➜ Deployment
