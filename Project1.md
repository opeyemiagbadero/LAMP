
##WEB STACK IMPLEMENTATION (LAMP STACK) IN AWS ##

I opened an AWS account, spined up an EC2 instance  with a Ubuntu Server OS.

![0  Creating an instance in AWS](https://user-images.githubusercontent.com/79456052/174342319-50ddc7a4-a53c-4391-a527-9406cc7998ee.png)

I Changed premissions for the private key file (.pem), using the chmod 0400 command to prevent errors and connected to my EC2 on my mac terminal

 ![1](https://user-images.githubusercontent.com/79456052/174344978-88ad52a8-be59-42d8-8127-7ba374b5929c.png)
  
I Installed  Apache on my ubuntu server using Ubuntu’s package manager 'apt' i.e the sudo apt update command 
  
![2  sudo apt update](https://user-images.githubusercontent.com/79456052/174345551-17268c17-bcf3-499b-a5d9-a6aedcb3f414.png)
  
 and the sudo apt install apache command

  ![3  sudo apt install apache2](https://user-images.githubusercontent.com/79456052/174346236-cd109a41-56f5-4686-be6e-f4b953882740.png)
  
 I verified that apache2 is running as a Service on the ubuntu OS using the command sudo systemctl status apache2
  
  ![4  sudo systemctl status apache2](https://user-images.githubusercontent.com/79456052/174347258-c807d72e-69e2-4a08-b164-bcee2dd06b2b.png)

  I added  the HTTP to EC2 configuration to open inbound connection (in addition to SSH i.e port 22) under the security group of my instance through port 80:
  
  ![Screenshot 2022-06-17 at 18 22 20](https://user-images.githubusercontent.com/79456052/174348716-b2b24153-828a-45d9-be44-2a7b9939340b.png)
  
  I Opened a web browser to access the  url http://44.204.88.253:80
  
![5  Apache2 Ubuntu Default Page](https://user-images.githubusercontent.com/79456052/174350015-56eb7fc8-e98a-49cf-a122-eac5957c22f2.png)
  
 I inputted the command $ sudo mysql
  
I used ‘apt’ to acquire and install mysql server using the command  sudo apt install mysql-server

  
![6  installing mysql server](https://user-images.githubusercontent.com/79456052/174351102-48d3d7e4-5ac3-48ec-bf5b-9583a7f736e2.png)
  
  
I logged into MYSQL console by inputting the command $ sudo mysql

  
![7  Connection to the MYSQL server](https://user-images.githubusercontent.com/79456052/174352991-08dc38c8-9399-4886-b85d-692db6fc3bf9.png)
  
 I installed php and confirmed the version
  
  
  ![9  installation of PHP packages sudo apt install php](https://user-images.githubusercontent.com/79456052/174354551-525dfff1-1e32-4c50-98e1-c9ce9aabd256.png)
  
![10  php -v](https://user-images.githubusercontent.com/79456052/174354561-d8db640d-63e4-461b-86ae-4995d5c5d097.png)
  
  
  In creating a virtual host for my website using apache, I created the directory for projectlamp, assigned ownership of the directory with my current system user and created and opened a new configuration file in Apache’s sites-available directory using vim editor. 
  
  ![11  assigining ownership of the directory with the current system user](https://user-images.githubusercontent.com/79456052/174355394-69306d4d-2470-40fb-973b-fcacb30489c0.png)
  
  I create an index.html file in thethe web root /var/www/projectlamp directory so that as to test that the virtual host works as expected:  
  
  ![12 enable the vitual host and make sure the config file doesnt contain sntax error and finally reloading Apache](https://user-images.githubusercontent.com/79456052/174355618-f3d70afa-d87a-42d8-8f44-1f18837793b3.png)
  
  
 I opened the  website URL using IP address: http://44.204.88.253:80
  
  
 ![13  open your browser and try to open your website URL using IP address](https://user-images.githubusercontent.com/79456052/174355732-fa21c9e0-aec6-4c56-8158-96637a75eff4.png)
  
 I editted the /etc/apache2/mods-enabled/dir.conf file so as to  change the order in which the index.php file is listed within the DirectoryIndex directive, reloaded apache2 and created a new file named index.php inside the custom web root folder, added the text  <?php
phpinfo(). 
 

![14  code before the final result](https://user-images.githubusercontent.com/79456052/174355747-ad343219-4d93-4af8-a728-02aa69af8608.png)
  
  I saved,  closed the file and  refreshed the page.

![final result](https://user-images.githubusercontent.com/79456052/174355776-607119d0-10ca-464e-b813-71ff7cc47737.png)  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
