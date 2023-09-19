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


