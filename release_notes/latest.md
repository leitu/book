# Version 0.4 (2015-09-15)

In Version 0.4, Hyper moves the hypervisor runtime into [runV](https://github.com/hyperhq/runv) project,
which [implements](https://github.com/opencontainers/specs/blob/master/implementations.md) the [OCI Specs](https://github.com/opencontainers/specs).

## Highlight features

- The hypervisor support is moved to runV.
- Eliminates the dependency on Docker Daemon, i.e. Users do not have to install Docker before installing hyper any more.

## Other improvements

- Merged Mac supporting code back to master branch, then the following feature are supported on Linux too:
  - Image management functions, including `pull`, `push`, `images`, `rmi`, `commit`.
  - Support build standard Docker image with `Dockerfile.`
  - Support `--rm` flag for `run` command, now it can automatically remove a Pod, when finished.
  - Support remove multiple Pod in one `rm` command line.
- Support port mapping configuration in `run` command line.
- Many bug fixes.

More details on the web site [(http://hyper.sh)](http://hyper.sh/).
