###command to check if virtualbox is correctly installed 
>vboxmanage 

###command to check if vagrant is installed correctly
>vagrant

###command to 'execute' vagrant file
vagrantup

#Command for checking the list of running vms
vboxmanage list runningvms

#ssh into the acs box for installation of ansibles
vagrant ssh acs

#install ansible using sudo account
sudo apt-get install ansible

#verify ansible is installed
ansible

#exit from ubuntu to install ansible on CentOS based box
exit

#ssh into CentOS based box named 'Web'
vagrant ssh web

#install enterprise release version of dependencies
sudo yum install epel-release

#install ansible
sudo yum install ansible

#verify ansible is installed correctly
ansible

#exit from 'web' box 
exit

#login to 'db' box to build ansible from scratch
vagrant ssh db

#ensure gcc compiler is installed
sudo yum install gcc

#install python setup tool
sudo yum install python-setuptools

#install python index packager
sudo easy_install pip

sudo yum install python-devel

#install ansible by downloading code & compiling it
sudo pip install ansible

#this did not work due to dependency on Python 2.6 which seems to be not supported

exit

#connect back to acs server
vagrant sh acs

#create directory called 'excercise1'
mkdir excercise1
cd excercise1
ls

#create basic inventory file
vi inventory

#check contents of inventory file
cat inventory

#execute a ping command
#uses a specific machine with the ip, this could be replaced with 'all' or '*' to run the same module on all the machines
#-u specifies the user which is vagrant in this case
#-m specifies the module, which is ping in this case
#-k prompt interactively for password
ansible 192.168.33.20 -i inventory -u vagrant -m ping -k

#add ssh to the known host files entry for web
ssh vagrant@192.168.33.20

#add ssh to known host files entry for db
ssh vagrant@192.168.33.30

#if the SSH pass error shows after this, install the package using command
sudo apt-get install sshpass

#verify that everything is fine uisng the debug mode (-v switch)
ansible 192.168.33.20 -i inventory -u vagrant -m ping -k -v

#verify that everything is fine uisng the debug mode for level 2(-vv switch)
ansible 192.168.33.20 -i inventory -u vagrant -m ping -k -vv

#verify that everything is fine uisng the debug mode level 3(-vvv switch)
ansible 192.168.33.20 -i inventory -u vagrant -m ping -k -vvv

#run adhoc commands
ansible all -i inventory -u vagrant -m command -a "/usr/sbin/yum update -y"

#command is default module, same can be achived by ommiting command keyword
ansible all -i inventory -u vagrant -m -a "/usr/sbin/yum update -y"





