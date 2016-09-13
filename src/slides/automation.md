# Automation

  - Replace manual steps with one action: `git push`

## Current State

  - Role, Application, and Library cookbooks built with Jenkins
    - Check the "automatic-garbanzo" github project
    - Jenkins responds to Github webhook, does heavy lifting
    - Multibranch job "builds" each branch, deploys artifacts for "prod"
      branch

  - Role cookbooks need an additional step, the creation of the policy object

  - Environment cookbooks aren't automated yet (but close)
    - Likely very similar to the automatic-garbanzo
    - Instead of artifact upload, `berks apply`

  - Automating Jenkins is not trivial  &#9785

---
