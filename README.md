# phemmy_lamp_stack_project
Lamp stack course project

I registered for a free profile account on AWS and having done that I launched an instance using the linux operating system (Ubuntu) and created a keypair which was downloaded to my local download folder.

From the CLI I changed directory into the downloads folder where my keypairs were located and proceeded to connect or "ssh-ed" to my AWS instance, hence transitioning into a pure linux operating system.

As with standard practices I proceeded to update my operating system using the "sudo apt update" command.

![Screenshot 2023-09-16 120425](https://github.com/FemiDare/phemmy_lamp_stack_project/assets/140294606/6edaed36-17b1-4036-847c-383885420f13)

![Screenshot 2023-09-16 120655](https://github.com/FemiDare/phemmy_lamp_stack_project/assets/140294606/d83850ea-3a56-4e94-a25f-df7cf0a0140d)

I then proceeded to install apache2 on my instance using the command "sudo apt install apache2" and then ran the "sudo systemctl status apache2" command to check/verify that apache2 was properly installed on my instatnce.

![Screenshot 2023-09-16 121003](https://github.com/FemiDare/phemmy_lamp_stack_project/assets/140294606/b5b7c6de-69aa-4827-8245-f52a12cbf205)

So as to be able to receive traffic from our webserver, I went to ahead to add an inbound rule via the security tab in my AWS instance so as to open TCP port 80 which is the default port that web browsers use in accessing web pages from the internet.

![Screenshot 2023-09-16 121318](https://github.com/FemiDare/phemmy_lamp_stack_project/assets/140294606/0764fe47-951f-4eed-a713-c1249b11fe82)

![Screenshot 2023-09-16 121502](https://github.com/FemiDare/phemmy_lamp_stack_project/assets/140294606/53846d87-7d49-4955-93fc-060b6d23ed1f)

I then tested to check if I could access my server from my ubuntu shell using the command "curl http://localhost:80" 

![Screenshot 2023-09-16 121647](https://github.com/FemiDare/phemmy_lamp_stack_project/assets/140294606/cd7c7b40-66ff-46de-b12a-59a6f25406d6)

![Screenshot 2023-09-16 121706](https://github.com/FemiDare/phemmy_lamp_stack_project/assets/140294606/1665835f-ef34-4ec5-90c6-5803a3681543)

I also tested to see if my apache server can receive requests from the internet via the web browser by using the url http://<my-public-ip-address>:80 

![Screenshot 2023-09-16 121940](https://github.com/FemiDare/phemmy_lamp_stack_project/assets/140294606/21d9a2d8-fbfd-4a90-bfbd-7bb91da08deb)

Next I proceeded to install my database management system (MySql) using the command "sudo apt install mysql-server" and then proceeded to log into mysql console using the command "sudo mysql" and exited the mysql console

![Screenshot 2023-09-16 122245](https://github.com/FemiDare/phemmy_lamp_stack_project/assets/140294606/9e9c6a75-2f3d-4e38-bc80-5c7802dc668d)

![Screenshot 2023-09-16 122637](https://github.com/FemiDare/phemmy_lamp_stack_project/assets/140294606/ab2e4bba-930c-4570-9d30-68b17789e799)

I then went ahead to configure a password for mysql console taking into consideration and selection several options as pertaining to the level of security and protocols for password acceptance and strenght using the command "sudo mysql_secure_installation" 

![Screenshot 2023-09-16 123516](https://github.com/FemiDare/phemmy_lamp_stack_project/assets/140294606/c2194cd6-db8d-4731-8b55-1ce0aad1498d)

![Screenshot 2023-09-16 123609](https://github.com/FemiDare/phemmy_lamp_stack_project/assets/140294606/5a4b881b-d7ec-4575-b635-7c7b4300788b)

So as to test the password I had just assigned, I logged into mysql console using the command "sudo mysql -p" which required I input the password before logging in and then exited using the command "exit" 

![Screenshot 2023-09-16 123918](https://github.com/FemiDare/phemmy_lamp_stack_project/assets/140294606/4be754f9-8005-45bc-8696-888754ac6634)

Next I proceeded to execute a php installation using the command "sudo apt install php libapache-mod-php php-mysql", libapache-mod-php being needed to enable apache to to handle php files and php-mysql being needed to allow php to communicate with mysql-based databases.

![Screenshot 2023-09-16 124135](https://github.com/FemiDare/phemmy_lamp_stack_project/assets/140294606/4491694d-1626-465a-bc44-c5cf57502637)

I then acertained my php version by using the command "php -v" 

![Screenshot 2023-09-16 124245](https://github.com/FemiDare/phemmy_lamp_stack_project/assets/140294606/b79a8f86-ae0c-47d8-b3bc-c9d5028a1c9f)

In order to change the loading protocol or behavior of the pages or set the priority in order of loading of pages, the settings of order of priority needed to be changed and I did that using the "sudo vim /etc/apache2/mods-enabled/dir.conf" command and moved a file named "index.php" forward in the order of load priority and then I reloaded apache using the command "sudo systemctl reload apache2"

![Screenshot 2023-09-16 124943](https://github.com/FemiDare/phemmy_lamp_stack_project/assets/140294606/78120aa6-baf8-4ea4-ae9e-74ba2c6fc11f)

![Screenshot 2023-09-16 125546](https://github.com/FemiDare/phemmy_lamp_stack_project/assets/140294606/b3340c54-b811-4233-8610-949e0b570833)

![Screenshot 2023-09-16 124737](https://github.com/FemiDare/phemmy_lamp_stack_project/assets/140294606/c1a16ce2-88f2-44d2-9a5b-f6eb8f1d22bb)

![Screenshot 2023-09-16 124859](https://github.com/FemiDare/phemmy_lamp_stack_project/assets/140294606/e2e3c07f-a19e-4d06-a99c-17d9ab86440f)

In order to test that php is working properly I was required to create a php script. I tried creating a file named "index.php" using the command "vim /var/www/projectlamp/index.php" but I keep receiving an error message as the file could not be created. I then proceeded to (more stressfully) change directory in where I wanted to create the file and using the "touch" command, created the file and then using the "vi" command edited the contents of the file.

![Screenshot 2023-09-16 131615](https://github.com/FemiDare/phemmy_lamp_stack_project/assets/140294606/c5917a9b-b6fe-4675-83c8-9622ce1dde7a)

![Screenshot 2023-09-16 131643](https://github.com/FemiDare/phemmy_lamp_stack_project/assets/140294606/e697acc7-9f4e-4159-9e7a-30ca0b2105f0)

![Screenshot 2023-09-16 131715](https://github.com/FemiDare/phemmy_lamp_stack_project/assets/140294606/ed0c92e7-8251-40dc-b25b-436664c63d03)

![Screenshot 2023-09-16 131118](https://github.com/FemiDare/phemmy_lamp_stack_project/assets/140294606/71ec5c14-42fb-4629-a994-b96123925b3b)

On editting the contents of this file, I went over to the web browser and reloaded the page with my public address as the url and the page had changed to the php info given the script that was added to the index.php file

![Screenshot 2023-09-16 131737](https://github.com/FemiDare/phemmy_lamp_stack_project/assets/140294606/3b610fa0-9ca6-46bf-a777-a92834486405)

Kindly note that in order to get this page to work as intended, I encountered quite a number of issues and had to trouble shoot and wiggle around before getting the desired result.

![Screenshot 2023-09-16 140459](https://github.com/FemiDare/phemmy_lamp_stack_project/assets/140294606/e0b03b4c-cebe-4ee6-a4f2-706a7c5af995)

![Screenshot 2023-09-16 140647](https://github.com/FemiDare/phemmy_lamp_stack_project/assets/140294606/ffcecee9-c4b5-498c-add3-2db0c34e436d)

![Screenshot 2023-09-16 140543](https://github.com/FemiDare/phemmy_lamp_stack_project/assets/140294606/2b1ebf53-632f-4dc6-88b6-1c79aaef4396)

![Screenshot 2023-09-16 140305](https://github.com/FemiDare/phemmy_lamp_stack_project/assets/140294606/b7f8fc6e-587e-449d-9cb2-d1bb653ee573)

![Screenshot 2023-09-16 140706](https://github.com/FemiDare/phemmy_lamp_stack_project/assets/140294606/af0a99bf-a726-4e2d-a587-943da6421d63)


