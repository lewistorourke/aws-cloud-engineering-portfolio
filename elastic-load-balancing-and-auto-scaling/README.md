
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

Successfully created and attached an additional Amazon EBS volume to an EC2 instance and reviewed how storage persists independently of compute resources.

---
