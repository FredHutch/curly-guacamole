# Policy Objects

 - role + cookbooks + environment = policy

## Role

Roles define:

  - attributes
  - run list &#9733

## Environment

Environments define:

  - attributes
  - cookbook versions &#9733

---

# Policy Objects

  - Role defines the cookbook(s) to be used
  - Environment defines the version of a cookbook to use
    - Versioning is important because different versions of a cookbook may have
      different features and capabilities
    - This is particularly critical when using 3rd party (i.e. community)
      cookbooks as we don't control releases

> _N.B.:_ A node may have multiple roles!

---
