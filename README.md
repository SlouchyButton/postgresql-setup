# postgresql-setup

## Requires

### BuildRequires
- m4
- docbook-utils
- help2man
- elinks (pretty README.rpm-dist)
- postgresql-server (detect current version)

### Requires
- coreutils

### Suggested BuildRequires
- util-linux (mountpoint utility)

### Maintainer's BuildRequires
- autoconf
- automake
- autoconf-archive

## Maintainer notes
- Be careful about paths. Your might need to tweak paths either in configure
  files, or in code based on your environment.

### Build instructions
1. `autoreconf -vfi`
2. `./configure --prefix=/usr`
    - Prefix needed for fedora environment - one of the path tweaks that are needed
3. `make`

If no init system is present, PostgreSQL server can be run after initialization
via `/usr/bin/pg_ctl -D /var/lib/pgsql/data -l /var/lib/pgsql/srv.log start`