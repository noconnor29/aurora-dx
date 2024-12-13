[![Build Image](https://github.com/noconnor29/aurora-dx/actions/workflows/build.yml/badge.svg)](https://github.com/noconnor29/aurora-dx/actions/workflows/build.yml)

# Purpose

This repository is meant to be a template for building your own custom Universal Blue image. This template is the recommended way to make customizations to any image published by the Universal Blue Project:
- [Aurora](https://getaurora.dev/)
- [Bazzite](https://bazzite.gg/)
- [Bluefin](https://projectbluefin.io/)
- [uCore](https://projectucore.io/)
- [main](https://github.com/ublue-os/main/)
- [hwe](https://github.com/ublue-os/hwe/) 

This template includes a Containerfile and a Github workflow for building the container image. As soon as the workflow is enabled in your repository, it will build the container image and push it to the Github Container Registry.

# Prerequisites

Working knowledge in the following topics:

- Containers
  - https://www.youtube.com/watch?v=SnSH8Ht3MIc
  - https://www.mankier.com/5/Containerfile
- rpm-ostree
  - https://coreos.github.io/rpm-ostree/container/
- Fedora Silverblue (and other Fedora Atomic variants)
  - https://docs.fedoraproject.org/en-US/fedora-silverblue/
- Github Workflows
  - https://docs.github.com/en/actions/using-workflows

# How to Use

## Template

Select `Use this Template` and create a new repository from it. To enable the workflows, you may need to go the `Actions` tab of the new repository and click to enable workflows.

## Containerfile

This file defines the operations used to customize the selected image. It contains examples of possible modifications, including how to:
- change the upstream from which the custom image is derived
- add additional RPM packages
- add binaries as a layer from other images

## Workflows

### build.yml

This workflow creates your custom OCI image and publishes it to the Github Container Registry (GHCR). By default, the image name will match the Github repository name.

#### Container Signing

Container signing is important for end-user security and is enabled on all Universal Blue images. It is recommended you set this up, and by default the image builds *will fail* if you don't.

### Examples
- [m2os](https://github.com/m2giles/m2os)
- [bos](https://github.com/bsherman/bos)
- [homer](https://github.com/bketelsen/homer/)
