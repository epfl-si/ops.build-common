# Useful Notes

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
