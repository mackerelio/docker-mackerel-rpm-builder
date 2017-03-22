# mackerel-rpm-builder

## What's this

This Docker image is used to build RPM packages in Dockernized envirionment.  It's based on [CentOS official Docker image](https://hub.docker.com/_/centos/).

This image is intended to build [mackerel-agent](https://github.com/mackerelio/mackerel-agent), but maybe you can use this image to build another packages.

## Usage

Use `docker run ...` instead of `rpmbuild` command.

Following example will work as `rpmbuild -bb ./SPEC.spec` and the artifact will be placed to `./rpmbuild/RPMS/`.

```
$ docker run --rm -v "$(PWD)":/workspace -v "$(PWD)/rpmbuild":/rpmbuild astj:docker-mackerel-rpm-builder -bb SPEC.spec
```

## Tags

- `c5` : based on `centos:5`
- `c6` : based on `centos:6`
- `c7` : based on `centos:7`
