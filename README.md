# Ansible-Dynamic_Manage-EC2-AWS
This configuration will connect ansible to your aws account allowing you to dynamically configure ec2 instances using Ansible by use of playbooks or ad-hoc commands. 

# Prerequisites 
You would need ssh access set up on your servers
Also you would need an AWS Access Key and AWS Secret Access Key configured on the server you're running the commands on for this to work

# Steps to set up the configuration

1. Create a python virtual evnvironment, command below
 python3 -m venv .env 

2. Next source the env / turn on the env, command below
 source .env/bin/activate

3. Install the Dependencies from the requirements.txt, command below
 pip install -r requirements.txt 

4. Install the Dynamic Inventory PlugIn, command below
 ansible-galaxy collection install amazon.aws 

5. Create your EC2 Configuration file (example included in Repo aws_ec2.yaml) You may have to modify based on your account settings

6. Next you can see a list of the ec2 instances on your accout, command below
 ansible-inventory -i aws_ec2.yaml 

7. Test your connection/configuration by running an ad-hoc command or playbook
 example..... ansible tag_Role_webserver -i aws_ec2.yaml -m ping

 on the above command I have a few of my instances tagged with a Role of webserver. I also included a basic playbook in the repo as an example as well. 


 