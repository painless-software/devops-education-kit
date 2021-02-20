Dev(Sec)Ops Education Kit
=========================

> Modern software development is safe and fast, reproducible and automatic.

Easy to Get Started
-------------------

- Cloud-native (resilient + scalable)
- Minimal prerequisites for (local) development
- One command to take off, avoid custom solutions + tools
- Fully automated deployment, fully scripted one-off setup

> e.g. `docker-compose up` (or similar)

Branching + Development
-----------------------

- Keep it as simple as possible
- A single main branch + topic branches (short-lived!)
- Write tests for every single feature + every bugfix
- Use feature toggles to control feature releases (not branches!)

> Use branching to ensure only working code is merged into your main branch. Don't use it to control feature releases.

Environments + Deployment
-------------------------

- Local ➜ Development ➜ Integration ➜ Production
- Static code analysis ➜ vulnerability scanning ➜ unit tests ➜ other tests (fastest first)
- Tag build artifacts with your source code commit SHA (audit trail)
- Triggers:
  1. **Open MR/PR:** Build review app ➜ deploy to Development
  2. **Merge MR/PR:** Build app ➜ deploy to Integration
  3. **Push Git tag:** Deploy app to Production (don't build it again!)

> Deploy every single, working feature directly. Give your PO control over the feature flags – not your release ceremony.
