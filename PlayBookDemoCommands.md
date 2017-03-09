###Create ansible configuration (ansible.cfg) file containing reference to inventory
#####Contents of the configuration
[defaults]
hostfile = inventory

###Create inventory file containing list of machines

###Create playbook file named web_db.yaml
####Ensure proper spacing is maintained between the names for plays, tasks, services etc.

###Execute the playbook
>ansible-playbook web_db.yaml

###Create a failure scenario by removing autherntication parameters for dbservers

###Unable to reproduce this as we need to provide the vagrant password using the -k flag

###Assuming there was an error, the retry file could be used to rerun the failed parts
>ansible-playbook web_db.yaml --limit @/home/vagrant/web_db.yaml.retry

##Adanced features
- Include files
- Include variables
- Grab output of other tasks
- Debug module 
- Playbook Handlers : Special tasks executed when notified. Executed only once at the end when all other tasks are executed
- Conditional clause
	When
-Templates : uses Jinja2 Engine

###Need to make sure that /var/www/html/ansible direcory exists on the web1 server
