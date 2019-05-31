# External dependencies for the building and installation of iRODS

Currently tested on:

- Ubuntu 12
- Ubuntu 14
- Ubuntu 16
- CentOS 6
- CentOS 7
- Debian 9

# Assumptions

This repository is expected to build in a VM or container environment that is isolated from other software or build environments.

The automated scripts run commands as `sudo` and update system libraries and compilers, etc.

# Installation

Before building the software listed in this repository, their own prerequisites must be met.

This is handled as automatically as possible with the `install_prerequisites.py` script.

```
./install_prerequisites.py
make
```

To only build the components for the iRODS Server:
```
make server
```

For CentOS 6, the included compilers are too old to build clang.

After the prerequisites are in place, make sure to use the newly installed g++.

```
./install_prerequisites.py
export CC=/opt/rh/devtoolset-2/root/usr/bin/gcc
export CXX=/opt/rh/devtoolset-2/root/usr/bin/g++
make
```
