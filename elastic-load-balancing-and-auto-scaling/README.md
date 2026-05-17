
## Amazon EBS Hands-On

### Project Overview

In this hands-on project, I explored Amazon Elastic Block Store (EBS) volumes and learned how to create, attach, and manage persistent block storage for EC2 instances.

This exercise demonstrated how EBS volumes provide durable storage that can be attached to EC2 instances, and how the "Delete on Termination" setting determines whether volumes are preserved when an instance is terminated.

---

## Objectives

- Review EBS volumes attached to an EC2 instance
- Navigate to the EBS Volumes console
- Create a new EBS volume
- Ensure the volume is created in the correct Availability Zone
- Attach the volume to an EC2 instance
- Verify multiple volumes are attached
- Understand volume persistence after instance termination
- Review the Delete on Termination setting

---

## AWS Services Used

- Amazon Elastic Compute Cloud (EC2)
- Amazon Elastic Block Store (EBS)

---

## Practical Tasks Completed

### Reviewed Existing EC2 Storage

Selected an existing EC2 instance and navigated to:

- EC2 Console
- Instances
- Select Instance
- Storage Tab

Viewed the root EBS volume already attached to the instance.

### Accessed the EBS Volumes Console

Navigated to:

- EC2 Console
- Elastic Block Store
- Volumes

Reviewed all EBS volumes available in the AWS account.

### Created a New EBS Volume

Created an additional EBS volume with the following configuration:

- Volume Type: General Purpose SSD (gp3 or gp2)
- Size: Custom
- Availability Zone: Same as the target EC2 instance

### Attached the Volume to the EC2 Instance

Attached the newly created volume by selecting:

- Actions
- Attach Volume
- Select EC2 Instance
- Confirm Attachment

### Verified Multiple Volumes

Returned to the EC2 instance Storage tab and confirmed that both:

- Root volume
- Additional EBS volume

were attached to the instance.

### Reviewed Availability Zone Requirement

Confirmed that EBS volumes must be created in the same Availability Zone as the EC2 instance.

If the volume is created in a different Availability Zone, it cannot be attached.

### Investigated Delete on Termination

Reviewed the `Delete on Termination` attribute for the root volume.

This setting determines whether the volume is automatically deleted when the EC2 instance is terminated.

- Enabled: Volume is deleted
- Disabled: Volume is preserved

---

## Storage Concepts Demonstrated

- Block Storage
- Persistent Storage
- Root and Additional Volumes
- Availability Zone Constraints
- Volume Attachment
- Data Retention
- Delete on Termination

---

## Key Lessons Learned

- EBS provides persistent block storage for EC2 instances.
- Additional volumes can be created and attached at any time.
- Volumes must reside in the same Availability Zone as the target instance.
- Data stored on EBS persists independently of the EC2 instance unless configured otherwise.
- The Delete on Termination setting controls whether volumes are retained after instance deletion.
- Preserving volumes is useful for backups, recovery, and data retention.

---

## Skills Demonstrated

- EBS Volume Creation
- EC2 Storage Management
- Volume Attachment and Verification
- Availability Zone Planning
- Data Persistence Configuration
- AWS Infrastructure Administration

---
## Outcome

## Amazon EBS Snapshots Hands-On

### Project Overview

In this hands-on project, I created Amazon EBS Snapshots to back up EBS volumes, copied snapshots to other AWS Regions, restored volumes from snapshots, and configured the AWS Recycle Bin to protect snapshots from accidental deletion.

This exercise demonstrated how AWS provides durable, point-in-time backups and disaster recovery capabilities for EC2 storage.

---

## Objectives

- Create point-in-time EBS snapshots
- View and manage snapshots in the AWS Console
- Copy snapshots to another AWS Region
- Restore new EBS volumes from snapshots
- Configure AWS Recycle Bin retention rules
- Recover accidentally deleted snapshots

---

## AWS Services Used

- Amazon Elastic Block Store (EBS)
- Amazon EBS Snapshots
- AWS Recycle Bin
- Amazon EC2

---

## Practical Tasks Completed

### Created an EBS Snapshot

Created a snapshot from an existing EBS volume by navigating to:

- EC2 Console
- Volumes
- Select Volume
- Actions
- Create Snapshot

This generated a point-in-time backup of the selected EBS volume.

### Viewed Existing Snapshots

Navigated to:

- EC2 Console
- Elastic Block Store
- Snapshots

Reviewed all snapshots stored in the AWS account.

### Copied a Snapshot to Another Region

Selected a snapshot and chose:

- Actions
- Copy Snapshot

Specified a destination AWS Region.

This is useful for:

- Disaster recovery
- Geographic redundancy
- Cross-region backups

### Restored a Volume from a Snapshot

Created a new EBS volume from a snapshot by selecting:

- Snapshots
- Select Snapshot
- Actions
- Create Volume from Snapshot

Configured:

- Volume type
- Size
- Availability Zone

Verified that the restored volume appeared in the Volumes section.

### Configured AWS Recycle Bin

Navigated to:

- AWS Recycle Bin

Created a retention rule to protect EBS snapshots from permanent deletion.

Configured:

- Resource type: EBS Snapshots
- Retention period: Custom duration

### Deleted and Recovered a Snapshot

Deleted a snapshot and confirmed that it was moved to the Recycle Bin.

Recovered the snapshot from the Recycle Bin, demonstrating protection against accidental deletion.

---

## Backup and Recovery Concepts Demonstrated

- Point-in-Time Backups
- Snapshot-Based Recovery
- Cross-Region Replication
- Disaster Recovery
- Data Retention Policies
- Accidental Deletion Protection

---

## Key Lessons Learned

- EBS snapshots provide incremental point-in-time backups of EBS volumes.
- Snapshots can be copied to other AWS Regions for disaster recovery.
- New EBS volumes can be restored directly from snapshots.
- AWS Recycle Bin protects snapshots from accidental deletion.
- Retention rules provide additional backup safety and governance.
- Snapshot-based backups are a core component of resilient AWS architectures.

---

## Skills Demonstrated

- EBS Snapshot Creation
- Cross-Region Backup Management
- Volume Restoration
- Disaster Recovery Planning
- AWS Recycle Bin Configuration
- Data Protection Administration

---
## Outcome

Successfully created EBS snapshots, copied them across regions, restored new volumes, and configured AWS Recycle Bin to protect backups from accidental deletion.

---
## Amazon Machine Images (AMI) Hands-On

### Project Overview

In this hands-on project, I created a custom Amazon Machine Image (AMI) from an existing EC2 instance and used it to launch new EC2 instances with the same operating system, applications, and configuration.

This exercise demonstrated how AMIs can be used to rapidly deploy preconfigured servers, significantly reducing setup time and ensuring consistency across environments.

---

## Objectives

- Launch and configure an EC2 instance
- Create a custom AMI from the configured instance
- View custom AMIs in the AWS Console
- Launch new EC2 instances from the custom AMI
- Understand how AMIs speed up deployments
- Reuse application and operating system configurations

---

## AWS Services Used

- Amazon Elastic Compute Cloud (EC2)
- Amazon Machine Images (AMI)
- Amazon Elastic Block Store (EBS)

---

## Practical Tasks Completed

### Launched and Configured an EC2 Instance

Created an EC2 instance and configured:

- Key pair
- Security groups
- Storage
- User data scripts
- Installed applications

This instance served as the base system for the custom AMI.

### Created a Custom AMI

Created an image from the configured EC2 instance by navigating to:

- EC2 Console
- Instances
- Select Instance
- Image and Templates
- Create Image

Provided a name and description, then initiated image creation.

### Verified AMI Creation

Navigated to:

- EC2 Console
- Images
- AMIs

Confirmed the newly created AMI appeared in the **My AMIs** section after reaching the `Available` state.

### Launched a New Instance from the AMI

Created a new EC2 instance and selected the custom image under:

- Application and OS Images
- My AMIs

The new instance inherited:

- Operating system configuration
- Installed software
- Security settings
- Preconfigured user data and applications

### Observed Faster Deployment

Verified that launching from the AMI was significantly faster than rebuilding the server manually, as all customisations were already included.

---

## Infrastructure Concepts Demonstrated

- Golden Images
- Immutable Infrastructure
- Rapid Provisioning
- Configuration Standardisation
- Pre-Baked Server Templates
- Scalable Deployments

---

## Key Lessons Learned

- AMIs are reusable templates containing the operating system and configuration of an EC2 instance.
- Custom AMIs enable consistent deployments across environments.
- Applications and settings are preserved in the image.
- Launching from an AMI is much faster than manually configuring a new server.
- AMIs form the foundation of Auto Scaling Groups and automated infrastructure.

---

## Skills Demonstrated

- EC2 Instance Configuration
- AMI Creation and Management
- Infrastructure Standardisation
- Rapid Server Deployment
- Immutable Infrastructure Concepts
- AWS Automation Foundations

---

## Outcome

Successfully created a custom Amazon Machine Image (AMI) from a configured EC2 instance and used it to launch new preconfigured instances, demonstrating rapid and consistent server deployment.

---


---
