###run the command inside production directory
ansible webservers -i inventory_prod -m user -a "name={{username}} password=12345" -k --sudo

###run the command in the group_vars direcctory
ansible webservers -i ../inventory_prod -m user -a "name={{username}} password=12345" -k --sudo

###run the command in the host_vars directory
>ansible webservers -i ../inventory_prod -m user -a "name={{username}} password=12345" -k --sudo