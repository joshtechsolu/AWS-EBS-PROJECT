# AWS-EBS-PROJECT
AWS EBS
In the shared responsibility model for EC2 storage, AWS is responsible for securing and managing the underlying infrastructure that powers storage services like EBS (Elastic Block Store) and EFS (Elastic File System). This includes the physical servers, networking, virtualization layer, and durability of volumes and snapshots. AWS ensures that the storage is highly available, resilient, and can be encrypted both at rest and in transit.

As the customer, you are responsible for how you configure and use storage. This includes attaching and mounting volumes, applying correct file system permissions, patching your operating system, setting IAM roles and policies, enabling encryption where needed, and ensuring backups are taken. You also control access via security groups and must protect your data from unauthorized access or accidental deletion.


 Steps I Took

Logged into the AWS Management Console and opened the EFS service.

Created a new Elastic File System (EFS) and left most default settings for simplicity.

Added a mount target in the same VPC and subnet as my EC2 instance.

Installed the required mount helper:




Challenges Faced

Mount helper not installed: Initially got a “mount command not found” error. Solved it by installing the amazon-efs-utils package.

Security group blocking traffic: Had to adjust the security group to allow NFS traffic (port 2049) between the EC2 instance and the EFS mount target.

File permissions: The mounted folder required sudo access, so I updated ownership to the EC2 user for easier testing.
