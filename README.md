# Semantic Versioning

## Overview

From [semver.org](https://semver.org/):

Given a version number MAJOR.MINOR.PATCH, increment the:

    MAJOR version when you make incompatible API changes,
    MINOR version when you add functionality in a backwards-compatible manner, and
    PATCH version when you make backwards-compatible bug fixes.

Additional labels for pre-release and build metadata are available as extensions to the MAJOR.MINOR.PATCH format.

## Practical Examples

### Example 1: Project in development

We're setting up a new project, it's internal only right now, but we'd still like to publish versions to make sure they work OK - we can use the **0.x.x** prefix to denote a package which is in development, e.g.

`0.0.1` - Very first version, probably doesn't even work!  
`0.0.2` - Minor fix from `0.0.1` to make it work  
`0.1.0` - We added some new features. Bump the `MINOR` version number and reset `PATCH` to zero.  
`0.1.3` - We fixed a couple of bugs from the `0.1.0` release  
`1.0.0` - It's production ready!

When we move from `0.x.x` to `1.x.x` we've increased the `MAJOR` version. That means if you're using `0.x.x` you should almost definitely upgrade to `1.x.x`, **but** you will definitely need to change your code because there will be breaking changes

### Example 2: Version 2.0!

Our project is becoming very successful, but we need to make some major API changes to add some new features, so we're going to push version `2.0.0`.

Any users of `1.x.x` *don't have to upgrade* to `2.0.0`, but if they do they should expect to change their code because there almost certainly will be breaking changes.

### Example 3: I found a bug in Version 1.5.2

You're latest version is now `2.1.3`, but there are people still using `1.5.2` because they're too ~~lazy~~ busy to upgrade.

You can still fix it!

Even if your latest version is `2.1.3`, you can still create a bugfix release and publish `1.5.3`. This won't affect users on `2.1.3` and will only apply to those on the `1.x.x` branch.

### Example 4: I need to demo 'Feature X' to a customer

This curveball is where Semantic Versioning can really help out. In addition to the standard `MAJOR`, `MINOR` and `PATCH` we've already mentioned, we can also use a `PRE-RELEASE` flag, which looks like this:

`2.1.3-alpha.0`

Which basically means that it's got everything that's in `2.1.3` plus also some alpha features that haven't been tested.

It's important to note that users of version `2.1.3` will not receive updates for `2.1.3-alpha.0` *unless they explicitly ask for it*.

You can create as many pre-releases as you like and you can also use any alphanumeric character, plus hyphens ([reference](https://semver.org/#spec-item-9)), e.g.

`2.1.3-screen-masking.15784`