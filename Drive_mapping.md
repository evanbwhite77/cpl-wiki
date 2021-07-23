CPL is moving to a model of having dedicated VMs for partners, with
links to dedicated VMs for individual projects. This page outlines the
process for establishing \"mapped drives\" from a partner VM to a
project VM.

A partner VM is the \"source\" VM where that partner\'s datasets are
stored. A project VM is the \"destination\" VM and which hosts any
analysis, code and research output. A \"mapped drive\" is a permanently
linked folder containing data that lives on the partner VM but is
accessible via the project VM.

Drive mapping allows users to access partner data from the project VM,
by simply navigating to a drive. This allows data files to be stored on
the CPL Data Hub once, but be accessible by multiple project teams in a
secure way.

## **Set up** {#set_up}

To set up mapped drives, make sure the following is already in place:

-   Dedicated partner VM(s) exist

```{=html}
<!-- -->
```
-   Data folders are set up. **NOTE** that all folders and sub-folders
    containing data must also contain the partner name/acronym i.e.
    CSAC_project_data so that they are easily identifiable once they are
    mapped to the project VM.

```{=html}
<!-- -->
```
-   Each user must be properly DARF\'ed for access to *both* the project
    and any partner VMs. User passwords must be the same between the
    partner VM and the project VM.

Once VM users are fully DARF\'ed and has credentials for both the
project VM and any partner VMs to be mapped, they should ask the IT
manager to develop a script to map the relevant folders, and specify the
following:

-   The project VM that the drives will be mapped to

```{=html}
<!-- -->
```
-   The file path for the subfolders on the partner VM(s) to be mapped
    (this is where the data is stored)

```{=html}
<!-- -->
```
-   The letters for each mapped drive.

## **Drive letters** {#drive_letters}

Each linked folder is assigned letter to become a \"mapped drive\" on
the destination VM. All VM users must use the same letter allocation.

For new projects, the remaining drive letters that are available to
assign are K: through Z: excluding S:, which used for the Commons share.
Drive mapping will be setup by IT Manager when user access to VM and
share folder is established.

Once you choose a letter or letters for your mapped drives, please log
this in the following section.

## **Record of Mapped Drives by project** {#record_of_mapped_drives_by_project}

**Student Supports**

On the Student Supports VM, once they run the drive mapping script (on
the desktop) users will see the following drives. Please contact Anna
Doherty for more information.

-   G: (CSAC)\\\\192.168.1.50\\OriginalData\\CSAC_Student_Supports

```{=html}
<!-- -->
```
-   H: (CDSS)\\\\192.168.1.51\\CDSS\\CDSS_project_data

```{=html}
<!-- -->
```
-   I: (CCCCO)

```{=html}
<!-- -->
```
-   J: (UCOP)

**Student Supports File paths for DARFs**

*CCCCO data*

-   CCCCO VM - E:\\OriginalData\\CCCCO_Student_Supports (read)

```{=html}
<!-- -->
```
-   Student Supports VM - E:\\Projects\\Student
    Supports\\data\\CCCCO_hash (read/write)

*CSAC data*

-   CSAC VM - E:\\OriginalData\\CSAC_Student_Supports (read)

```{=html}
<!-- -->
```
-   Student Supports VM - E:\\Projects\\Student
    Supports\\data\\CSAC_hash (read/write)

*CDSS data*

-   CDSS VM - E:\\CDSS\\CDSS_project_data (read)

```{=html}
<!-- -->
```
-   Student Supports VM - E:\\Projects\\Student
    Supports\\data\\CDSS_hash (read/write)

*UCOP data - To be created*

-   UCOP VM - E:\\OriginalData\\UCOP_Student_Supports (read)

```{=html}
<!-- -->
```
-   Student Supports VM - E:\\Projects\\Student
    Supports\\data\\UCOP_hash (read/write)