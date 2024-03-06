## Project description

I am a security professional working at a health care company. As part of my job, I’m required to regularly update a file that identifies the employees who can access restricted content. The contents of the file are based on who is working with personal patient records. Employees are restricted access based on their IP address. There is an allow list for IP addresses permitted to sign into the restricted subnetwork. There's also a remove list that identifies which employees you must remove from this allow list.

My task is to create an algorithm that uses Python code to check whether the allow list contains any IP addresses identified on the remove list. If so, you should remove those IP addresses from the file containing the allow list.

## Open the file that contains the allow list
To open the file containing the allow list I use the following command:

![image](https://github.com/JustA-Byte/Python-SQL-Labs/assets/161458321/0afa4d53-e7bb-439d-9efb-1500657c9c9d)

Assigning the file to a variable allows me to call it later in the code.

I use the with keyword to handle the ```open()``` function, calling the ```import_file``` variable I assigned earlier as the first parameter and ```“r”``` as the second parameter; I then pass this to ```file``` to deal with the contents in the imported file in the following steps.

## Read the file contents
Following on; I assign a new variable inside the ```open()``` function called ```ip_addresses``` and store the read contents of the imported file inside.

![image](https://github.com/JustA-Byte/Python-SQL-Labs/assets/161458321/9cb46fbc-8d77-442e-973c-4d619e0a1225)


I then display the contents of ```ip_addresses``` to verify the imported contents have been stored correctly. The output consisted of a single string consisting of the ip addresses within the file. They are all separated by single line spaces and need converting into a list format to be easily passed through in future code.

## Convert the string into a list
To convert the string data into a list, I can use the ```split()``` method on the ```ip_addresses``` variable.

![image](https://github.com/JustA-Byte/Python-SQL-Labs/assets/161458321/11ce4f63-bbaf-4fa8-8555-d40bd89bd6cf)

## Iterate through the remove list
Now I need to build an iterative statement which will be used to remove ip addresses displayed in the variable ```remove_list``` from the ip addresses shown in ```ip_addresses```. Initially I'll just build the ```for``` statement to print each element contained within ```ip_addresses```.

![image](https://github.com/JustA-Byte/Python-SQL-Labs/assets/161458321/fb71655e-4ae5-4b15-bf15-5f4b0793e379)

## Remove IP addresses that are on the remove list
To remove the IP addresses that are on the remove list I now need to build a conditional statement within the ```for``` statement I previously made. This will assess each element within the ```remove_list``` and where necessary will remove the item from the ```ip_addresses``` variable using the ```.remove()``` method. 

To verify the IP addresses have been removed I will print contents of the ```ip_addresses``` variable prior to and after the use of the ```for``` loop.

![image](https://github.com/JustA-Byte/Python-SQL-Labs/assets/161458321/b027bcd5-b4b0-40b9-97bb-d766c12c5a9b)

## Update the file with the revised list of IP addresses 
To update the original file that was used to create the ```ip_addresses``` list I now need to use the ```.join()``` method to convert the list of data within the ```ip_addresses``` variable back to a string. 

Following that I'll then use the with statement again which will rewrite the original file and delete the original contents replacing them with the new data.

![image](https://github.com/JustA-Byte/Python-SQL-Labs/assets/161458321/367e5aa1-63b4-4560-8b3e-9554a7141050)

## Summary
In summary, the combined code above allows me to import a file, read file data, Change the data type,loop through variables and remove relevant ip addresses, Convert data again and write to a file overriding the existing data. In doing this it has automated a process which will have taken a while to go through the ip addresses manually and remove one's no longer needed on the access list through the use of iteration in for loops.

The code in its entirety can be seen below:
![image](https://github.com/JustA-Byte/Python-SQL-Labs/assets/161458321/d7a52373-be77-41f7-965e-eb98320dbb78)
![image](https://github.com/JustA-Byte/Python-SQL-Labs/assets/161458321/6826c609-b036-4a64-8fbb-3511de524f80)





