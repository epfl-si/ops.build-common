# Useful Notes

## ssh configuration

Add this to your `~/.ssh/config` to wield the authority of `idevfsd-checkouter` when cloning out of c4science:

```
Host c4science.ch
     ForwardX11 no
     # Next line required if you use an ssh-agent(1) (whose keys would otherwise have priority):
     IdentityAgent /dev/null
     IdentityFile /keybase/team/epfl_si.build_common/id_rsa_c4science_idevfsd-checkouter
```
