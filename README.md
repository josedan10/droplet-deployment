# droplet-deployment

## Clone repository into DO droplet

1. Create the droplet on Digital Ocean: https://docs.digitalocean.com/products/droplets/how-to/create/
2. Install Nginx: https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-ubuntu-20-04
```bash
sudo apt update
sudo apt install nginx
```

3. Install Git: https://git-scm.com/book/en/v2/Getting-Started-Installing-Git
```bash
sudo apt install git-all
```

4. Create a new user: https://www.digitalocean.com/community/tutorials/how-to-add-and-delete-users-on-ubuntu-20-04
```bash
sudo adduser newuser
```
5. Add user to sudoers:
```bash
usermod -a -G examplegroup exampleusername
```

6. Change to the new user: https://unix.stackexchange.com/questions/156962/how-to-change-to-normal-user-in-the-command-line-when-logged-in-as-the-root-user
```bash
su - username
```

7. Generate SSH key for the user and add it to Github: https://security.stackexchange.com/questions/143442/what-are-ssh-keygen-best-practices
```bash
ssh-keygen -t ed25519 -a 100
```

8. Add key to ssh agent: https://stackoverflow.com/questions/17846529/could-not-open-a-connection-to-your-authentication-agent
```bash
eval `ssh-agent -s`
ssh-add
```

9. Add permissions to create folders to the user: https://support.circleci.com/hc/en-us/articles/360003649774-Permission-Denied-When-Creating-Directory-or-Writing-a-File, https://askubuntu.com/questions/487527/give-specific-user-permission-to-write-to-a-folder-using-w-notation, https://stackoverflow.com/questions/20276895/could-not-create-work-tree-dir-example-com-permission-denied
```bash
sudo chown -R $USER /var/www
```

11. Clone the repo and change the folder name: https://graphite.dev/guides/git-rename-repo-while-cloning
```bash
git clone <REPOSITORY_URL> <NEW_DIRECTORY_NAME>
```


12. Create servers folders: https://www.digitalocean.com/community/tutorials/how-to-set-up-nginx-server-blocks-virtual-hosts-on-ubuntu-16-04
13. Config Nginx to work with domains ans subdomains: https://www.digitalocean.com/community/questions/how-to-setup-nginx-with-subdomain-only


## Register DNS record on Namecheap
https://www.namecheap.com/support/knowledgebase/article.aspx/10375/2208/how-do-i-link-a-domain-to-my-digitalocean-account/
