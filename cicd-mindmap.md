Continuous Delivery – CI/CD
===========================

```plantuml
@startmindmap
+[#lightcoral] Continuous\n   Delivery
++ Agile culture
+++ Pair programming
+++ Code review\n(MRs/PRs)
+++ Transparency
++++[#lightgray] Post-mortem
++++ Empower\nproduct owner
+++ Share\nresponsibility
+++ DevOps
++ Methodology
+++ Version control
++++ Branching model
+++ Writing tests
+++ Automatic releases\n(no manual tasks)
++++ Deploy early,\ndeploy often
++ Fast feedback\ncycles
+++ Tech debt\nmanagement
+++ Code quality\nmonitoring
++ CI/CD pipeline\n(automation)
+++ Automatic\n   builds
++++ Packaging
++++ Containerization
+++ Automated\n     tests
++++ Unit tests (TDD)
++++ Acceptance\ntest (BDD)
++++ Code coverage\n(≈ 100%)
+++ Automatic\nquality gates
++++ Fully automatic\ndeployment
+++++ Blue/green\ndeployment
+++++ Canary releases
++++ Feature toggles
-- Stable\napplications
--- Automatic\nload tests
--- Application\nmonitoring
----[#lightgray] Alerting
--- Exception\ntracking
--- Autoscaling
-- Secure\napplications
--- Vulnerability\nscanning
--- Security\nengineering
--[#lightgray] Self-healing\napplications
---[#lightgray] Automatic\nrollback
---[#lightgray] Automatic\noperations
--[#lightgray] Policy\nenforcement
-- Immutable\ninfrastructure
--- Infrastructure\n     as code
--- Locked-down\nenvironments
--- Tear down & rebuild
---- Automatic\nbackup & restore
@endmindmap
```

Related Resources
-----------------

- [Google Engineering Practices Documentation](https://google.github.io/eng-practices/) (code reviews)
- [Google Site Reliability Engineering](https://sre.google/sre-book/table-of-contents/) (SRE)
- [What is CI/CD?](https://about.gitlab.com/topics/ci-cd/) (GitLab)
- [What is DevOps?](https://about.gitlab.com/topics/devops/) (GitLab)
- [What is DevOps?](https://www.atlassian.com/devops) (Atlassian)
- [Continuous Delivery](https://painless.software/continuous-delivery) (Painless Software)
