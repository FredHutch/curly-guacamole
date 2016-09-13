# Working with Chef

  - The exact steps depend on the need

## New Hosts

  - Adding new hosts to existing roles- just bootstrap

        `knife bootstrap --run-list role[cit-base] ...`

## Changes to Existing Roles

  - Update the cookbook(s) and check in changes
  - Rev the cookbook and create a release
  - Update the environment with the new role version
  - Deploy the environment

---

# Working with Chef

## New Applications

  - Create a role that configures _just_ the application
  - Rely on base roles to configure the basic stuff

---

