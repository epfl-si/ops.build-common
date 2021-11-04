# Useful Notes

## About

Automated operations to build the docker base image on openshift for the
«dinfo»'s applications.

1. Pull and host the latest `httpd:burster` docker image
2. Manage the ssh key to git clone the private repo
3. Get the code and the Dockerfile from https://c4science.ch/diffusion/1989/
4. Rewrite the `FROM: debian:burster` to `httpd:burster`
5. Build the image (BuildConfig and ImageStream)
6. Enjoy image from `docker-registry.default.svc:5000/dinfo-cicd/cadi-libs-idevfsd:latest` or `os-docker-registry.epfl.ch/dinfo-cicd/cadi-libs-idevfsd:latest`

## Credentials

In order to use this repository, you need to

- be a member of the `epfl_si.build_common` [Keybase](https://keybase.io) team
- have access to the `dinfo-cicd` OpenShift namespace (request access with [Camptocamp](mailto:support-infrastructure@camptocamp.com))


## ssh configuration

Add this to your `~/.ssh/config` to wield the authority of `idevfsd-checkouter` when cloning out of c4science:

```
Host c4science.ch
     ForwardX11 no
     # Next line required if you use an ssh-agent(1) (whose keys would otherwise have priority):
     IdentityAgent /dev/null
     IdentityFile /keybase/team/epfl_si.build_common/id_rsa_c4science_idevfsd-checkouter
```
