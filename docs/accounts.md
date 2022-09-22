# Accounts and Allocations
## Eligibility
Employees and students with `ucdenver.edu` or `cuanschutz.edu` login credentials. 
External collaborators with VPN access, sponsored by a faculty member, 
upon approval.

## How to get an account

Please use [this form](https://forms.office.com/r/GQ9ef7ei4i) to request accounts and allocations requests. **The form should be filled by a faculty member and list users in their group, such as students or external collaborators.** External collaborators need a POI with VPN access first.

The form asks for the CU Denver email addresses for all accounts to be created, and

* a brief description of the project (few words is OK),
* funding source, if any
* promise include an acknowledgement of the NSF grant 2019089 in all publications and presentations, and send us at least the citation.

This is needed for reporting to the funding agency (annual reports, quad charts, PI meetings, etc.)

## Resources and Allocations
**To encourage early use, storage and core time limits are not enforced for an initial period - we want you to work here**! They will be activated in future as needed to keep the resources available fairly for everyone.

### Storage 
**Users are responsible for maintaining copies of their important files elsewhere. Files can be lost, even with backups.** 
 
* **Home directories** – 25GB, more with an allocation request. Backed up weekly, keeping 4 backups from various times. Home directories are `/home/user`, usually implemented as soft links. 
* **Project storage** -  250GB, more with an allocation request. **Not backed up.** Project directories are in  `/storage/department/projects/name`, often implemented as soft links. A project directory can be shared between a group of users.
* **Scratch** - no limit, not backed up. Files with oldest access date will be purged automatically when the scratch space usage is over 80%. Please make your own subdirectories in `/scratch`.

### Cores
* **Small** - up to 30,000 Alderaan core hours, max 128 concurrent cores per user, standard storage. Automatic with an account.
* **Medium** - up to 150,000 Alderaan core hours, max 640 concurrent cores, additional storage.
* **Large** - larger than medium. 

Jobs are charged for the total reserved core time, whether used or not. 
Jobs on Alderaan GPU/high memory nodes are charged for all 64 cores on the node. 

Core time on other clusters than Alderaan is not limited.
### Transitional

Existing home directories under 25GB are being migrated to backed-up space. **Existing home directories larger than 25GB are not backed up**. Users should bring their home directories under the limit so that they can be migrated to backed-up space. 

Existing projects get initial storage allocation equal to the current use + 10% + the standard project quota. 

## Old files
 
Upon project or user inactivation, the files will be deleted after a notification (if the user's university email still works) and a grace period. 


