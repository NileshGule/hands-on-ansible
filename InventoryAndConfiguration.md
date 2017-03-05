###Create excercise folder
>mkdir excercise_4.1
>cd excercise_4.1
>ls

###Initiate Inventory
>vim inventory

####Add contents of inventory

###Run ping command by specifying username & password in the inventory file
>ansible web1 -i inventory -m ping -k

####Note the above command does not work without putting the -k switch for time being