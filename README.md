Induction to OCI Compliant Image Management
===========================================

# Overview
[That project](https://github.com/infra-helpers/container-image-building)
documents how to manage the life-cycle (_e.g._, specification, building,
storage on registries, deployment, deletion) of Open Container Initiative
(OCI) images. See the section below for more details on OCI.

## Extract from the OCI Image Format project overview
The [OCI Image Format project](https://github.com/opencontainers/image-spec)
creates and maintains the software shipping container image format
spec (OCI Image Format).

The OCI Image Format partner project is the
[OCI Runtime Spec project](https://github.com/opencontainers/runtime-spec).
The Runtime Specification outlines how to run a
["filesystem bundle"](https://github.com/opencontainers/runtime-spec/blob/master/bundle.md)
that is unpacked on disk. At a high-level an OCI implementation would download an OCI Image
then unpack that image into an OCI Runtime filesystem bundle.
At this point the OCI Runtime Bundle would be run by an OCI Runtime.

This entire workflow supports the UX that users have come to expect from container engines
like Docker, podman and rkt: primarily, the ability to run an image with no additional arguments:
```bash
$ docker run example.com/org/app:v1.0.0
$ podman example.com/org/app:v1.0.0
$ rkt run example.com/org/app,version=v1.0.0
```

To support this UX the OCI Image Format contains sufficient information to launch the application
on the target platform (e.g. command, arguments, environment variables, etc).

## References
* [Open Container Initiative (OCI)](https://www.opencontainers.org/)
  + [GitHub - OCI image format project)](https://github.com/opencontainers/image-spec)
  + [GitHub - OCI image format specification](https://github.com/opencontainers/image-spec/blob/master/spec.md)
  + [GitHub - OCI runtime specification](https://github.com/opencontainers/runtime-spec)
* [YouTube - What are containers?, Sep. 2017, Scott McCarthy](https://www.youtube.com/watch?time_continue=20&v=rlj0UZlvGp0)
* [Podman](https://github.com/containers/libpod) / [Buildah](https://github.com/containers/buildah)
  + [RedHat Blog - Podman - Running containers with shareable `systemd` services](https://www.redhat.com/sysadmin/podman-shareable-systemd-services)
  + [RedHat Blog - Podman and Buildah for Docker users, Feb. 2019, William Henry](https://developers.redhat.com/blog/2019/02/21/podman-and-buildah-for-docker-users/)
  + [RedHat Blog - Podman for MacOS (sorrt of), Feb. 2020, Rarm Nagalingam](https://developers.redhat.com/blog/2020/02/12/podman-for-macos-sort-of/) 
  + [ITNext Blog - Podman and Skopeo on MacOS, Dec. 2019, Balazs Szeti](https://itnext.io/podman-and-skopeo-on-macos-1b3b9cf21e60)
  + [OpenSource.com - Podman: A more secure way to run containers, Oct. 2018, Daniel Walsh](https://opensource.com/article/18/10/podman-more-secure-way-run-containers)
  + [RedHat Blog - Buildah - Speeding up container image builds, Mar. 2020, Daniel Walsh](https://www.redhat.com/sysadmin/speeding-container-buildah)
* [Kata containers](https://katacontainers.io/), open source container runtime,
  building lightweight virtual machines that seamlessly plug into
  the containers ecosystem
* [CoreOS `rkt` (pronounce "rocket" project)](https://coreos.com/rkt/), a security-minded,
  standards-based container engine
* [CRI-O project](https://cri-o.io), lightweight container runtime for Kubernetes (k8s)
* Comparison
  + [StackOverflow - How `containerd` compares to `runC`, Jan. 2017](https://stackoverflow.com/a/41646558/798053)
  + [Medium - Container runtimes: clarity, Feb. 2018, Antonio Murdaca](https://medium.com/cri-o/container-runtimes-clarity-342b62172dc3)
  + [YouTube - Next Generation Tools for container technology, May 2018, Daniel Walsh](https://www.youtube.com/watch?v=msdaf3lBOn0)
  + [OpenSource.com - A history of low-level Linux container runtimes, Jan. 2018, Daniel Walsh](https://opensource.com/article/18/1/history-low-level-container-runtimes)
* General
  + [mkdev Blog - Dockerless: Which tools to replace Docker with and why, May 2019, Kirill Shirinkin](https://mkdev.me/en/posts/dockerless-part-1-which-tools-to-replace-docker-with-and-why)
  + [RedHat Blog - The limits of compatibility and supportability with containers, May 2019, Scott McCarthy](https://www.redhat.com/en/blog/limits-compatibility-and-supportability-containers)
  + [OpenSource.com - A sysadmin's guide to containers, Aug. 2018, Daniel Walsh](https://opensource.com/article/18/8/sysadmins-guide-containers)

