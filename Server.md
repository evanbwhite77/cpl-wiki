## Server organization {#server_organization}

All data analysis done at CPL is performed on one of CPL\'s secure,
remote servers. See [this
PPT](https://drive.google.com/open?id=1UX5zJxykUroA4YRNZuX8MAw92G1Hl3kv)
for an overview of CPL\'s IT.

CPL\'s projects are found in the E: drive. To access any given folder on
the server, you first must complete a project-specific
[DARF](https://drive.google.com/open?id=1fqUf3XI9mxb5grOII-pon1SULDdWkaDN)
with Irfan and April.

## Logging on to the server {#logging_on_to_the_server}

Detailed steps available here: [IT
Training](https://drive.google.com/open?id=1UX5zJxykUroA4YRNZuX8MAw92G1Hl3kv)

**The very basics:**

1\. Connect to the VPN

2\. Enter server address and your login credentials into your
computer\'s remote desktop program

3\. Look for a 2-Factor Authentication (Duo) push to your phone

## Uploading to the server {#uploading_to_the_server}

Whether you\'re uploading new data, ado files, or a MS Word document,
the mechanics for uploading to the server are the same. The only
exception is when a partner is sending sensitive or identified data
directly to the server from their own system. In these situations,
alternate arrangements are made (contact Irfan and April for more).

**Mechanics**

The mechanics of moving files onto the server are these:

1\. Connect to the VPN (link to guide for this)

2\. Connect to Jupiter via an FTP client (such as Filezilla) using your
log-in information sent to you by Irfan ([FTP guide
here](https://drive.google.com/open?id=11Rwu6BW2BcjLQ7vcBXSZ-ucrMnRsHI0D))

3\. Transfer files via the FTP

4\. Check the \"ftpsync\" folder on your server desktop. Within 5
minutes the transferred files should show up there

5\. Move the transferred files to the proper folder on the server.
Delete the files from the \"ftpsync\" folder

6\. In the event that the files are original data files that also need
to be backed up to the project\'s \"OriginalData\" folder, contact the
[CPL Help Desk](mailto:helpdesk@capolicylab.org)

## Downloading from the server {#downloading_from_the_server}

If you have identified files that you need downloaded off of the server,
email the [CPL Help Desk](mailto:helpdesk@capolicylab.org) with your
request and information on where to find the needed file (best practice:
create a \"to export\" folder within your project folder, put a copy of
the file you need downloaded there so that it is easy to find and to
keep track of what you\'ve downloaded in the past). The file will be
reviewed for potentially identifying information or other prohibited
data before it is downloaded.

In special cases where a file must be sent directly from the CPL server
to a partner, contact [Irfan Malik](mailto:irfan@cpl.ucla.edu).

## Stata package repository {#stata_package_repository}

If you\'re looking for a Stata package on any of CPL\'s VMs, go to
\"\\code\\stata\\packages\" on [The
Commons](https://www.wiki.capolicylab.org/index.php?title=Commons) to
see if it has already been put on the server by another user. If it has,
copy the .ado file from that package\'s sub-folder into the top level of
your user profile (\"C:\\Users\\**yourusername**\\ado\\plus\"). You
might have to create an \"ado\" folder and a \"plus\" folder inside of
it, if one is not present already. The package will be ready to use the
next time you launch Stata.

If the package you\'re looking for is not already on the server, follow
these steps:

1\. Download the ado, help, and any other necessary files to your local
computer

2\. Transfer the files from your local computer to the server via FTP
(see ([FTP
instructions](https://drive.google.com/open?id=11Rwu6BW2BcjLQ7vcBXSZ-ucrMnRsHI0D))
for more info on how to do this)

3\. On the server, move the transferred files from the \"ftpsync\"
folder on your desktop to the top level of your user profile
(\"C:\\Users\\**yourusername**\\ado\\plus\").

4\. Finally, email Irfan and ask him to place a copy of the package into
a new subfolder within **\\code\\stata\\packages** on The Commons.

## R package repository {#r_package_repository}

CPL maintains Cran-like (i.e., mini Cran) package repositories on the
[The Commons](https://www.wiki.capolicylab.org/index.php?title=Commons).
There are repos for different R versions like R 4.0.X and 4.1.X. Users
can install packages from the repo that matches their R version by
specifying the repo directory path in the `install.packages()` function.

For example, to install tidylog (a CPL-recommended package) on a VM
where you are using R 4.0.3 you would use the following code:

`install.packages("tidylog", repos = "`[`file:////commons/Commons/code/r/repo_4.0`](file:////commons/Commons/code/r/repo_4.0)`")`

Installation code and instructions are also available on [The
Commons](https://www.wiki.capolicylab.org/index.php?title=Commons) in
**code/r** for those who like to cut and paste long directories.

## cplChannel: Python package repository {#cplchannel_python_package_repository}

[cplChannel](https://docs.google.com/document/d/10sqWGfLFx_KVhiEzji6IQoISF4P6wzaktCpdUKbdHEo/edit?usp=sharing)
is a local repository of python libraries that lives in the Commons
folder at code/python/cplChannel, which is accessible to everyone. This
means that we can manage which libraries are available across all VMs
from a single source.

The primary advantage of having a CPL conda channel is that we can now
build project-specific conda environments that live within a project
folder and are useful for isolating the development environment for the
project. This means that each python project will have its own libraries
and python version such that any other user can enter the project
folder, activate the project-specific conda environment, and replicate
the code within the project. It also makes it easy to transfer the
environment and improve reproducibility, and reusability, of code.