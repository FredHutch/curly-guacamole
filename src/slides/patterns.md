# SciComp Patterns

## _role recipe_ pattern

  - the _role_ object is defined on the server with only the _role recipe_'s
    default recipe in the run list
  - the _role recipe_ runs additional recipes as necessary to configure the
    components for the role

## _environment recipe_ pattern

  - Very similar to an application cookbook
  - Contains only dependencies on our role cookbooks
  - Berksfile.lock is checked into SCM
  - One environment per branch (e.g. prod, dev, test, etc.)

---
