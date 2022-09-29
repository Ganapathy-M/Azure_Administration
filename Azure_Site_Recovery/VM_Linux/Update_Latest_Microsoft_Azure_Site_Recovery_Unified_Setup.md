# Update Latest Microsoft Azure Site Recovery Unified Setup in Configuration Server

### Before upgrading the configuration server or operating system/kernel versions, verify if the target version is supported Site Recovery

* Azure VM support
* VMware/physical server support
* Hyper-V support

Eg: VMware/physical server support

OS/Kernel Version (**Ubuntu 20.04 LTS**/**Kernel Versions:5.4.0-122-generic**)

### Review available updates to find out what you want to upgrade.

```
**Supported release**   **Mobility service version**    **Kernel version**
    20.04 LTS                       9.50	            5.4.0-1080-azure
                                                        5.4.0-1083-azure
                                                        5.4.0-1085-azure
                                                        5.4.0-1086-azure
                                                        5.4.0-113-generic
                                                        5.4.0-117-generic
                                                        5.4.0-120-generic
                                                        5.4.0-121-generic
                                                        5.4.0-122-generic
```
 
You run update rollups to update the configuration server. Updates can be applied for up to N-4 versions. For example:

* If you run 9.47, 9.48, or 9.49, you can upgrade directly to 9.50.
* If you run 9.46 or earlier and you want to upgrade to 9.50, you must first upgrade to version 9.47. before 9.50.

**With every new version 'N' of an Azure Site Recovery component that's released, all versions below 'N-4' are considered to be out of support.**

```
! Important

Official support is for upgrading from > N-4 version to N version. For example, if you're running you are on N-6, you need to first upgrade to N-4, and then upgrade to N.

```

### Upgrade to the latest Site Recovery version.

### Upgrade the operating system/kernel to the required versions.

### Reboot.

**This process ensures that the machine operating system/kernel is upgraded to the latest version, and that the latest Site Recovery changes needed to support the new version are loaded on to the machine.**






