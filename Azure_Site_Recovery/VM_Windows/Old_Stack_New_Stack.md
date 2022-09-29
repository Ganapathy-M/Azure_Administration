## Old Stack vs New Stack



**Process Server** - Compress and encrypted the replication datas send to the On-premises Master Target 

**Master Target Server** - Store the replication datas

**Inplace Recovery** - VMs are inplace (It only replicates the changes data)

**Outplace Recovery** - VMs Completely Gone (It will create the VMDK file in Vcenter datasource)

**Old Stack** -  It Requires S2S VPN for Failback and Linux Master Target Server 

**New Stack** - We dont need S2S VPN and Linux Master Target Server

