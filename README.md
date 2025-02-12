# dcos-cli-container
This is a Linux (debian) container containing the DC/OS CLI tool. This container provides a workaround for the current issue where MacOS Catalina no longer supports 32bit binaries. Until the issue has been fixed internally, we suggest you use this or one of the other workarounds described at https://support.d2iq.com/s/article/Customer-Advisory-MacOSCatalina-D2iQ-2019-0001

Set up an alias (pick a name that suits your workflow:

```alias mydcos='docker run -it --rm -e HOME=${HOME} -v ~/.dcos:${HOME}/.dcos -v $PWD:/dcos --workdir /dcos d2iqmdekkers/dcos-cli-container:1.2'```

You can replace `alias mydcos=[...]` with whatever you like, for example `alias dcos=[...]` but we advise you keep using the regular `dcos` command, and only use this workaround when you encounter a CLI subcommand that doesn't work. 

If you find another subcommand that doesn't work, please reach out to #dcos-cluster-ops if you are @D2iQ or open a support ticket and we can work towards adding the proper fix to make this work.

## Issues:
- You will have to remove and reinstall / setup existing clusters.
- The progress bars don't show, and when setting up a cluster or installing a package it appears that the command hangs. Use ```-v``` or ```-vv``` for output. 
- If you set `alias` to `dcos`, command completion works, ...slowly...

I hope we have an updated set of tools for OSX Catalina soon. In the meantime, this should work. 

Any issues or bugs, please mail or slack me. 

