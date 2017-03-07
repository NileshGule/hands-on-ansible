###Run the command to install httpd module using yum
>ansible webservers -i inventory -m yum -a "name=httpd state=present" -k --sudo

###Run the httpd service by starting it
>ansible webservers -i inventory -m service -a "name=httpd enabled=yes state=started" --sudo

###Install mysql server using yum
>ansible dbservers -i inventory -m yum -a "name=mysql-server state=present" -k --sudo

###start the database service
>ansible dbservers -i inventory -m service -a "name=mysqld state=started" -k --sudo

###Start the web server
>ansible webservers:dbservers -i inventory -m service -a "name=iptables state=stopped" --sudo -k

###Look at all the network interfaces for Web server
>ansible web1 -i inventory -m setup -a "filter=ansible_eth*" -k 