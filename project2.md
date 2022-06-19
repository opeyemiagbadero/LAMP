
##WEB STACK IMPLEMENTATION (LEMP STACK) IN AWS ##

I updated the server package to get Nginx installed using the commands sudo apt update and sudo apt install nginx

![1](https://user-images.githubusercontent.com/79456052/174483875-8884d5ea-2ab2-4b24-bb48-671a126f9939.png)

![2](https://user-images.githubusercontent.com/79456052/174483907-96a4ebac-9d3a-493a-be0b-b04b90f1f388.png)

To verify that nginx was successfully installed and running as a service in Ubuntu, I ran the sudo systemctl status nginx command

![3](https://user-images.githubusercontent.com/79456052/174483948-c4c06d9f-d29f-4b33-a6ed-0b6ed2e8974d.png)

I confirmed that Nginx server can respond to requests from the Internet by inputting the public ip address of the server on a web browser

![4](https://user-images.githubusercontent.com/79456052/174484125-68fa64f5-1175-4045-a95e-5b3f29d667b9.png)

I installed the mysql server using the same apt command i.e sudo apt install mysql-server and logged into mysql console

![5](https://user-images.githubusercontent.com/79456052/174484304-a5f5865b-6baa-4e15-9a8e-c6b1a9bf5ae5.png)

 
I set up a  password for the root user, using mysql_native_password as default authentication method, ran a script that will remove some 
insecure default settings and lock down access to my database system and confirmed that I could log in to the MySQL console by typing $ sudo mysql -p


![6](https://user-images.githubusercontent.com/79456052/174484412-795181d3-0a19-4561-aa64-c81e9d8c75af.png)

In the process of installing  PHP, I installed php-fpm, which and tells Nginx to pass PHP requests to the software for processing 
followed by  php-mysql, a PHP module that allows PHP to communicate with MySQL-based databases.


![7](https://user-images.githubusercontent.com/79456052/174484422-5a92bf25-bf6f-4cbb-a321-84021d3aa4ab.png)

In configuring Nginx to use PHP Processor, 
I created the root web directory for the your_domain,assigned ownership of the directory with the $USER environment variable, referencing my current system user, 
opened a new configuration file in Nginx’s sites-available directory and pasted in a configuration in the file.
I Activated my configuration by linking to the config file from Nginx’s sites-enabled directory, tested the config files for errors and reloaded nginx to
apply changes. I Created an index.html file in that location so that we can test that my new server block works as expected.

![8](https://user-images.githubusercontent.com/79456052/174485116-a4954c17-ae73-4493-8d4d-9f63595d77ee.png)

I opened my website URL using the the ip address http://44.204.67.181:80 to confirm that nginx was working as expected.

![Screenshot 2022-06-19 at 15 22 00](https://user-images.githubusercontent.com/79456052/174485841-546f4c88-366a-47c3-a839-0d42f6126894.png)

In testing php with nginx, i opened a new file called info.php in the /var/www/projectLEMP/ directory and copied a php code that will return information
about the server. I accessed the page in my web browser by visiting http://44.204.67.181/info.php set up in my Nginx configuration file.


![9](https://user-images.githubusercontent.com/79456052/174485960-d48bbb7b-225e-4297-875d-8c05ca65ccd8.png)

I connected to mysql server  console using my root account and created a database named example_database and a user named example_user. I 
confirmed that the new user has the proper permissions by logging in to the MySQL console again, using the command mysql -u example_user -p


![10](https://user-images.githubusercontent.com/79456052/174486261-d4a0d2cb-7ac6-4d63-885d-707d63baa054.png)

I confirmed access to the example_ database after  logging in to the MySQL console, created a test table named todo_list. followed by inserting a few rows of content in the test table. 

I then created a new PHP file in my  custom web root directory i.e /var/www/projectLEMP/todo_list.php, copied the given content and saved the file.


![15](https://user-images.githubusercontent.com/79456052/174487577-0d734d17-79ff-4d0e-a9fb-c48774b68a8d.png)


I opened the domain name or public IP address configured for my  website http://44.204.67.181 followed by /todo_list.php i.e http://44.204.67.181//todo_list.php


![16](https://user-images.githubusercontent.com/79456052/174488453-8a3dc756-9d94-4b83-b78b-b231ebf5a756.png)






