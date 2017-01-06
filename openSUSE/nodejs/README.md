### How to use this vagrant box?

I was facing some issues in provisioning the box with the `vagrant up` command. Tried debugging a bit and didn't get anywhere so gave up. `vagrant up` will successfully bring up the box. Run `vagrant provision` separately.

### Pre-requisites

##### Softwares

- **Vagrant**: I use version 1.8.5
- **VirtualBox**: I use version 5.1.4

##### Node projects to be setup

Create/Edit the yaml file `playbooks/roles/setup_node_projects/vars/git_repos.yml` and add a configuration similar to the one below (Haven't tested out how this works with repos with auth).

```yaml
repos:
  - git_url: <url of your repository>
    guest_dest_folder: <destination_folder_on_the_guest_machine> (This needs to be a subfolder of /opt/node_projects if you want to NFS share with your host machine)
  - git_url: <url of your repository>
    guest_dest_folder: <destination_folder_on_the_guest_machine>    
```