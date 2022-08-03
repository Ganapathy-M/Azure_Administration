# Microsoft Azure Backup Server (MABS) : Antivirus Exclusions

    Running a solid, constantly updated antivirus product on your servers, like your Microsoft Azure Backup Sever (MABS) v3, is a necessity to keep a healthy and secure server environment.

    However, with installing an antivirus product, you also risk having issues with certain workloads and services on those severs. Just like System Center Data Protection Manager (SCDPM), MABS is compatible with most antivirus software products. Though, these antivirus products can also affect MABS performance and, if not configured properly, can cause data corruption of replicas and recovery points.

    To avoid file conflicts and to minimize performance degradation between your MABS server and the antivirus software running on top of it, disable real-time monitoring by the antivirus software for the following processes and directories, which are all listed below.

**MABS processes to exclude from antivirus real-time monitoring**

`For information about configuring real-time monitoring based on process name or folder name, see your antivirus documentation.`

`**DPMRA.exe**`

(full path: C:\Program Files\Microsoft Azure Backup Server\DPM\DPM\bin\DPMRA.exe)

`**csc.exe (exclude when you experience degraded performance while using the MABS Administrator Console)**`

(full path: C:\Windows\Microsoft.NET\Framework\v4.0.30319\csc.exe) -> you can also exclude csc.exe in all the other Microsoft.NET Framework folders

`**cbengine.exe**`

(full path: C:\Program Files\Microsoft Azure Backup Server\DPM\MARS\Microsoft Azure Recovery Services Agent\bin\cbengine.exe)

# MABS directories in the MABS Program Files folder to exclude from antivirus real-time monitoring

