# Environment Cookbooks

  - The environment cookbook has only a `metadata.rb` file containing
    the role cookbooks that will operate inside this environment

## Example

  - Assume one environment for database servers and another for web servers
  - The *database* environment would have roles:
    - base
    - db\_server
  - The *web* environment would have roles:
    - base
    - apache
    - nginx

> The base role has rules common to any host.  Though note that the database
> and web environments could use different versions of the base role cookbook.

---

# Environment Cookbooks

`scicomp-env-database/metadata.rb`:

```
name 'scicomp-env-database'
version '0.1.0'

depends 'scicomp-role-base', '= 1.0.2'
depends 'scicomp-role-db_server', '= 2.1.7'
```

`scicomp-env-web/metadata.rb`:

```
name 'scicomp-env-web'
version '0.5.2'

depends 'scicomp-role-base', '= 0.9.5'
depends 'scicomp-role-apache', '= 4.0.1'
depends 'scicomp-role-nginx', '= 2.2.3'
```

---

# Environment Cookbooks

## Environment Branches

  - Each branch has a corresponding environment on the server
  - An environment cookbook `scicomp-env-web` with branches `prod` and
    `dev`, there would have these environment objects on the Chef server:

     - `scicomp-env-web` (the `prod` branch doesn't get a suffix)
     - `scicomp-env-web-dev`

  > The "-dev" environment has different version pins, presumable targetting
  > newer versions of cookbooks with additional features

---

# Environment Cookbooks

The environment for most SciComp nodes:

```
$ knife environment show scicomp-env-compute
chef_type:           environment
cookbook_versions:
  apt:                 = 4.0.1
  apt-chef:            = 1.0.0

  ...

  java:                = 1.39.0
  scicomp-base:        = 0.1.7
  scicomp-env-compute: = 0.1.2
  scicomp-roles:       = 1.2.8
  selinux:             = 0.9.0
  seven_zip:           = 2.0.1
  sudo:                = 2.9.0
  sysctl:              = 0.7.5
  vim:                 = 2.0.1
  windows:             = 1.44.1
  yum:                 = 3.11.0
  yum-epel:            = 0.7.0
default_attributes:
description:         Environment for Scientific Computing Compute Hosts
json_class:          Chef::Environment
name:                scicomp-env-compute
```

---
