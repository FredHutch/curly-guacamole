# DIVERTIMENTO: Role-recipe Pattern

This pattern defines a role object that only contains the default recipe of a cookbook with the same name as the role:

```
{
  "name": "scicomp-base",
  "description": "Minimal configuration to participate on Hutch Network",
  "json_class": "Chef::Role",
  "default_attributes": {

  },
  "override_attributes": {

  },
  "chef_type": "role",
  "run_list": [
    "recipe[scicomp-base]"
  ],
  "env_run_lists": {

  }
}
```

---
