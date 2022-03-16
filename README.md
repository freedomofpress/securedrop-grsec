securedrop-grsec
================

This is a Debian metapackage that installs our grsecurity-hardened
kernel and other related configuration.

## Build setup

```bash
$ sudo apt install git-buildpackage devscripts ubuntu-keyring
$ export BUILDER=pbuilder
$ DIST=focal git-pbuilder create --mirror http://archive.ubuntu.com/ubuntu --components "main restricted universe multiverse"
```

TODO: Document qubes bind-dirs configuration.

## Building

```bash
$ gbp clone https://github.com/freedomofpress/securedrop-grsec
$ cd securedrop-grsec
$ export BUILDER=pbuilder
$ DIST=focal git-pbuilder --update
$ gbp buildpackage
```

## Updating for a new version
```bash
$ make -f debian/rules update NEWVERSION=5.15.27
```

And then git commit everything, and build.
