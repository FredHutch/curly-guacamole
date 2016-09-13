# Role Cookbooks

A role cookbook is named for the role object it supports.

   - a role "server" will have a cookbook named "role" behind it
   - the "role" cookbook contains all the necessary recipes to configure the
     node
   - the role object will set its run list to the default recipe of the role
     cookbook

Roles get stacked up:

   - we have a "cit-base" role that configures a minimum of things that are
     globally acceptable for any node on the network
     - ntp
     - dns
   - then a "scicomp-base" role that configures the minimum for a node to be
     managed by SciComp:
     - sudoers
     - ssh keys

---

# Role Cookbooks

The role object on the server:

```
$ knife role show scicomp-base 
chef_type:           role
default_attributes:
description:         Minimal configuration to participate on Hutch Network
env_run_lists:
json_class:          Chef::Role
name:                scicomp-base
override_attributes:
run_list:            recipe[scicomp-base]
```

Note that the run list is more precisely indicated as:

```
run_list:            recipe[scicomp-base::default]
```

---

# Role Cookbooks

The recipe `scicomp-base/recipes/default.rb`:

```
# .
# Cookbook Name:: scicomp-base
# Recipe:: default
# .

...

include_recipe 'nscd::default'
include_recipe 'sudo::default'
include_recipe 'krb5::default'
include_recipe 'scicomp-base::keys'

# Create privilege separation directory
directory '/var/run/sshd' do
  owner 'root'
  group 'root'
  mode '0755'
  action :create
end

...
```

---

# Role Cookbooks

# Development

  - Check out, branch, and hack away
  - When tests succeed and the features are done:
    - merge to prod
    - version
    - upload itself and dependencies to server
    - upload to kwik-e-mart
  

---
