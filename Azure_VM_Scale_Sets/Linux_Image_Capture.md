# How to capture Linux VM in Azure

Open SSH to your VM (use azure public ip, root creds) and start VM’s deprovision

```
# waagent -deprovision+user -force
```

Now VM is ready for generalizing

```
# halt
```

*halt* this will shutdown the VM