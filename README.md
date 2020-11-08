# devops_engineers_assignment
Deploy an application on an eks cluster using Jenkins configured with Ansible

1. Implement and configure a cluster on AWS
  - go to eks-getting started
  - in that directory you can find all terraform scripts need provider.tf, output.tf, eks.tf
  - run the following commands
  ```sh 
  terraform init
  terraform apply
  ```
  - After finishng login to the launching console and connect to the instance via ssh
  
2. Install docker on EC2 instance and start services 
  ```sh 
  yum install docker
  service docker start
  ```

3. create a new user for Docker management and add him to Docker (default) group
```sh
useradd dockeradmin
passwd dockeradmin
usermod -aG docker dockeradmin
```

4. Install Ansible
Add a EPEL (Extra Packages for Enterprise Linux)third party repository to get packages for Ansible 
```sh 
rpm -Uvh https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
```

Install Ansible
```sh 
yum install ansible -y 
```

Check Ansible version 

```sh 
ansible --version
```

Create a new user for ansible administration & grant admin access to user (Master and Slave)
```sh 
useradd ansadmin
passwd ansadmin
# below command addes ansadmin to sudoers file. But strongly recommended to use "visudo" command if you are aware vi or nano editor. 
echo "ansadmin ALL=(ALL) ALL" >> /etc/sudoers
```
