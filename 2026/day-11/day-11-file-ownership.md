# Day 11 – File Ownership Challenge
Today I learned about file ownership in Linux. I practiced how to check which user and group owns a file and how to change them using chown and chgrp.

I also practiced changing both owner and group together and using -R to change ownership of files and directories inside a folder.

### Instructions

* Check file owner and group using ls -l
* Change owner using chown
* Change group using chgrp
* Change owner and group together
* Practice recursive ownership using -R
* Verify changes after every operation

### Important Commands


ls -l filename

sudo chown user filename

sudo chgrp group filename

sudo chown user:group filename

sudo chown -R user:group directory/


## My Practice

### 1. Check User and Ownership


whoami

id

ls -l


I confirmed that I was working with the ubuntu user.

### 2. Create Users and File


touch devops-file.txt

sudo useradd tokyo

sudo useradd berlin

sudo useradd nairobi

### 3. Practice chown


sudo chown tokyo devops-file.txt


sudo chown berlin devops-file.txt

ls -l devops-file.txt


### 4. Practice chgrp


touch team-notes.txt

sudo groupadd heist-team

sudo chgrp heist-team team-notes.txt

ls -l team-notes.txt


This changed the group ownership.

### 5. Owner + Group


touch project-config.yaml

sudo chown tokyo:heist-team project-config.yaml

mkdir app-logs

sudo chown berlin:heist-team app-logs


### 6. Recursive Ownership


mkdir -p heist-project/vault

mkdir -p heist-project/plans

touch heist-project/vault/gold.txt

touch heist-project/plans/strategy.conf


sudo groupadd planners

sudo useradd professor

sudo chown -R professor:planners heist-project/

ls -lR heist-project/



## What I Learned

* chown → changes owner

* chgrp → changes group

* chown user:group → changes both

* -R → applies changes recursively

* ls -l → verifies ownership


#90DaysOfDevOps

#DevOpsKaJosh

#TrainWithShubham
