# The Berkshelf Way

`berkshelf` manages cookbook dependencies, allows liberal use of 3rd party
cookbooks without losing one's sanity

  - Using community cookbooks quickly leads to dependency hell
  - Declare dependencies and let `berks` sort out which versions are required

---

# Basic `Berksfile`:

  - created by `chef generate cookbook`

```
source 'https://supermarket.chef.io'

metadata
```
  - indicates url of a server running the supermarket API
  - indicates that dependencies are located in the `metadata.rb` file

---

# Berks-ing

## Building the Lockfile

  - `Berksfile.lock` is a file containing a graph indicating cookbooks and
    versions required
  - `berks install` and `berks update` create and manage the file

## Updating the Chef Server

  - `berks upload` uploads the cookbook version to the server and freezes it
  - `berks apply <environment>` applies the versions to the environment

---

# What Berks is Managing

  ![:scale 100%](img/graph.png)

> This graph is generated by `berks viz`, using `graphviz` as the back-end for
> creating the image

---
