Environments + Deployment
=========================

- Local ➜ Development ➜ Integration ➜ Production
- Static code analysis ➜ unit tests ➜ other tests (fastest first)
- Vulnerability scanning:
  1. Base image
  1. App dependencies
  1. App code
- Tag build artifacts with your source code commit SHA (audit trail)
- Triggers:
  1. **Open MR/PR:** Build review app ➜ deploy to Development
  1. **Merge MR/PR:** Build app ➜ deploy to Integration
  1. **Push Git tag:** Deploy app to Production (don't build it again!)

> Deploy every single, working feature directly. Give your PO control over the feature flags – not your release ceremony.

Environments
------------

Each environment increases the confidence in a fully operational resulting
application that a work increment contributes to.

```plantuml
@startuml
title Environments

Local -> Development : Create or update\nmerge request
Development -> Integration : Merge\nmerge request
Integration -> Production : Tag release\n(version tag)

node Local {
}

node Development {
}

node Integration {
}

node Production {
}

@enduml
```

Deployment
----------

Based on blue/green deployment and stable container images we ensure that
both Integration and Production are in a fully operational state at all times.

```plantuml
@startuml
skinparam componentStyle rectangle
title Parallel Review Apps\n(Microservice Architecture)

node Development {
  component mr99 as "A mr99"
  component mr42 as "A mr42"
}

note top of mr99
  Microservice
  proves to run
  with minimal
  dependencies
  (functional tests)
end note

note bottom of Development
  MRs deploy
  independent
  service
  instances
end note

note bottom of mr99
  Deleted when
  MR is merged
end note

node Integration {
  component B
  component A
}

note top of Integration
  Microservices
  prove to run
  together
  (integration tests)
end note

note top of B
  Deployment
  proves to be
  frictionless
end note

note bottom of Integration
  Latest working
  version of each
  service is
  deployed
  automatically
end note

note bottom of B
  All checks and
  tests run again
  ..
  Production
  image is built
  (deleted when
  test suite fails)
end note

node Production {
  component B2 as "B"
  component A1 as "A"
}

note top of Production
  Deployed features
  can be selectively
  activated
  (feature toggles)
end note

note bottom of Production
  Latest working
  versions of all
  services that pass
  entire test suite
end note

note bottom of B2
  Blue/green
  deployment
  strategy keeps
  stable version
  in place
  ..
  Service scales
  automatically
  when load
  changes
end note

@enduml
```

Integration should be deleted and recreated afresh regularly (e.g. each week).

In an advanced approach, we could swap Production and Integration on each deployment.

Related Topics
--------------

- [Release notes](devops-branching.md) ➜ MR description
