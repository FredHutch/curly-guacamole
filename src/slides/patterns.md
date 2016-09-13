# Cookbook Patterns

## _role cookbook_ pattern

  - the _role_ object is defined on the server with only the _role recipe_'s
    default recipe in the run list
  - the _role recipe_ runs additional recipes as necessary to configure the
    components for the role

## _environment cookbook_ pattern

  - Defines dependencies only on role cookbooks
  - Used to resolve cookbook dependencies within an environment
  - `Berksfile.lock` is checked into SCM

  > This is important- by checking in a working lock file you can
  > revert to a previous environment should something break

---
