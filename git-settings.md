# Git settings
Here are few tricks and tips for git

## Manage multiple Git(Lab/Hub) accounts on a single machine with SSH keys
let’s assume we have the two GitLab accounts: 

* **Personal Account**, **_username_**: personal, **_email_**: personal@email.com
* **Work Account**, **_username_**: work, **_email_**: work@email.com

**Generate SSH keys for each user [Linux]**
* `` ssh-keygen -t rsa -b 4096 -C "personal@email.com" ``
* `` ssh-keygen -t ed25519 -C "work@email.com" ``

**Once you’re done, you will have two sets of SSH keys, e.g.:**

* `` cat ~/.ssh/id_rsa.pub `` (personal account)
* `` cat ~/.ssh/id_ed25519.pub `` (work account)
copy and paste ssh key to respective accounts

**Configure SSH to use the correct keys**
Now create the file `` ~/.ssh/config `` and add the following contents:

`` Host gitlab.com
    HostName gitlab.com
    User git
    IdentityFile ~/.ssh/id_rsa.pub
Host gitlab.com-work
    HostName gitlab.com
    User git
    IdentityFile ~/.ssh/id_ed25519.pub ``

**Cloning repositories**
* ***Personal***
``$ git clone git@gitlab.com:personal/repository.git``
* ***Work***
``$ git clone git@gitlab.com-work:work/repository.git``

**Updating existing repositories**
assuming your remote’s name is ``origin``
* ``$ git remote set-url origin git@gitlab.com-work:work/repository.git``

**Set local git configs**
* ``$ cd work-repository``
* ``$ git config user.name "Work Account"``
* ``$ git config user.email "work@email.com"``
