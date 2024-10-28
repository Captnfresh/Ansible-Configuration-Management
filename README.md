# Ansible-Configuration-Management

## Step 1 - Install and Configure Ansible on Ec2 instance

1. Update the `Name` tag on your `Jenkins` EC2 instance to `Jenkins-Ansible`. We will use this server to run playbooks.

![image 1]()

2. In your GitHub account, create a new repository named `ansible-config-mgt`. This repository will store your Ansible configurations, playbooks, and inventory files.

![image 2]()

3. Install Ansible on your Jenkins-Ansible ec2 instance. Update your package index:

```
sudo apt update
```

4. Install Ansible:

```
sudo apt install ansible
```
image 3

5. Verify the installation by checking the Ansible version:

```
ansible --version
```
image 4

Now that Ansible is installed, let's automate the integration between Jenkins and your GitHub repository:

6. Create a Jenkins Freestyle Project: Head over to Jenkins and create a new freestyle project called ansible.

image 5

7. Configure a webhook in GitHub and set the webhook to trigger ansible build.

image 6

image 7

8. Configure a Post-Build Action: configure a post-build action to archive all files generated during the build

image 8
























































