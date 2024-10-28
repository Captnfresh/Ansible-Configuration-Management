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

9. To confirm everything is functioning as expected: Make a minor change in the README.md file in the `main` branch of your GitHub repository. Push the changes and verify that Jenkins automatically triggers the build.

image 9

10. Check that the build artifacts are saved in the specified directory.
```
ls /var/lib/jenkins/jobs/Ansible/builds/1/archive/
```
image 10

### Note: Trigger Jenkins project execution only for main (or master) branch

Now the setup would be like this image below:

image 11

Also, Every time you Stop/Start your Jenkins-Ansible server, you hsve to configure github webhook to a new IP address. In order to avoid it, It only makes sense to allocate an Elastic IP to your Jenkins-Ansible Ec2 instance.

image 12


## Step 2 - Prepare Your Development Environment Using Visual Studio Code

The development phase of DevOps requires proper coding tools, and setting up your development environment in Visual Studio Code (VSC) will streamline your process:

1. Install Visual Studio Code:
   * Download and install Visual Studio Code.

2. After you have Successfully installed VSC, confifgure it to connect to your newly created GitHub Repository:

3. Clone Your Repository:
   * Clone the ansible-config-mgt repository to your Jenkins-Ansible EC2 instance:
     ```
     git clone <ansible-config-mgt repo link>
     ```

## Step 3 - Begin Ansible Development
     























































