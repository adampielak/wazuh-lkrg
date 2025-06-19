# Wazuh custom LKRG (Linux Kernel Runtime Guard) Decoders and Rules
This project contains custom LKRG decoders and rules for Wazuh

### Linux Kernel Runtime Guard (LKRG)
LKRG is a kernel module (not a kernel patch), so it can be built for and loaded
on top of a wide range of mainline and distros' kernels, without needing to
patch those.  We currently support kernel versions ranging from as far back as
RHEL7's (and its many clones/revisions) to latest mainline and distros kernels.

* Put rules and decoder files under `/var/ossec/etc/rules` and `/var/ossec/etc/decoders`

### Thanks
* Adam 'pi3' Zabrocki (http://pi3.com.pl)

### Todo
* Decoders
