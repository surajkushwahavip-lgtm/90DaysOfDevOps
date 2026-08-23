## Day 09 – Linux User & Group Management

Today I practiced Linux user, group and permission management on Ubuntu.

Users Created

Users created:

tokyo

berlin

professor

nairobi

sudo useradd -m tokyo
sudo useradd -m berlin
sudo useradd -m professor
sudo useradd -m nairobi

## Check users:

ls -l /home/
grep -E 'tokyo|berlin|professor|nairobi' /etc/passwd

## Passwords

sudo passwd tokyo
sudo passwd berlin
sudo passwd professor
sudo passwd nairobi

## Passwords were set successfully.

Groups

Created:

sudo groupadd developers
sudo groupadd admins
sudo groupadd project-team

## Check:

grep -E 'developers|admins|project-team' /etc/group

Group Assignment

sudo usermod -aG developers tokyo
sudo usermod -aG developers berlin
sudo usermod -aG admins berlin
sudo usermod -aG admins professor

## Verify:

groups tokyo
groups berlin
groups professor

## Result:

tokyo      -> developers
berlin     -> developers admins
professor  -> admins

## Shared Directory

## Create the developers workspace:

sudo mkdir -p /opt/dev-project
sudo chgrp developers /opt/dev-project
sudo chmod 775 /opt/dev-project

## Test with users:

sudo -u tokyo touch /opt/dev-project/tokyo-file.txt
sudo -u berlin touch /opt/dev-project/berlin-file.txt
ls -l /opt/dev-project/

## Team Workspace

sudo usermod -aG project-team nairobi
sudo usermod -aG project-team tokyo

sudo mkdir -p /opt/team-workspace
sudo chgrp project-team /opt/team-workspace
sudo chmod 775 /opt/team-workspace

Test:

sudo -u nairobi touch /opt/team-workspace/nairobi-test.txt
ls -l /opt/team-workspace/

## What I Learned

How to create Linux users and home directories.

How groups can be used to manage access for multiple users.

How chmod 775 and chgrp work with shared directories.

How to test file access using sudo -u.




## 90DaysOfDevOps #DevOpsKaJosh #TrainWithShubham
