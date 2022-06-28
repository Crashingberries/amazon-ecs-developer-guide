# Using data volumes in tasks<a name="using_data_volumes"></a>

Amazon ECS supports the following data volume options for containers\.
+ Amazon EFS volumes — Provides simple, scalable, and persistent file storage for use with your Amazon ECS tasks\. With Amazon EFS, storage capacity is elastic\. It grows and shrinks automatically as you add and remove files\. Your applications can have the storage that they need and when they need it\.  Amazon EFS volumes are supported for tasks that are hosted on Fargate or Amazon EC2 instances\. For more information, see [Amazon EFS volumes](efs-volumes.md)\.
+ FSx for Windows File Server volumes — Provides fully managed Microsoft Windows file servers\. These file servers are backed by a Windows file system\. When using FSx for Windows File Server together with Amazon ECS, you can provision your Windows tasks with persistent, distributed, shared, and static file storage\. For more information, see [FSx for Windows File Server volumes](wfsx-volumes.md)\.

  Windows containers on Fargate do not support this option\.
+ Docker volumes — A Docker\-managed volume that's created under `/var/lib/docker/volumes` on the host Amazon EC2 instance\. Docker volume drivers \(also referred to as plugins\) are used to integrate the volumes with external storage systems, such as Amazon EBS\. The built\-in `local` volume driver or a third\-party volume driver can be used\. Docker volumes are only supported when running tasks on Amazon EC2 instances\. Windows containers only support the use of the `local` driver\. To use Docker volumes, specify a `dockerVolumeConfiguration` in your task definition\. For more information, see [Docker volumes](docker-volumes.md)\.
+ Bind mounts — A file or directory on the host, such as an Amazon EC2 instance or AWS Fargate, is mounted into a container\. Bind mount host volumes are supported for tasks that are hosted on Fargate or Amazon EC2 instances\. For more information, see [Bind mounts](bind-mounts.md)\.

**Topics**
+ [Fargate task storage](fargate-task-storage.md)
+ [Amazon EFS volumes](efs-volumes.md)
+ [FSx for Windows File Server volumes](wfsx-volumes.md)
+ [Docker volumes](docker-volumes.md)
+ [Bind mounts](bind-mounts.md)