# Lab setup

## 01. damn vulnerable web application([dvwa](https://dvwa.co.uk/)):
Damn Vulnerable Web App (DVWA) is a PHP/MySQL web application that is damn vulnerable. Its main goals are to be an aid for security professionals to test their skills and tools in a legal environment, help web developers better understand the processes of securing web applications and aid teachers/students to teach/learn web application security in a class room environment.

What I did:
1. Pulled the docker image and created an container with it at port 80
2. exec into the docker pod
3. installed nano and fix missing configs in /etc/php/7.0/apache2/php.ini 
4. gave it an reCaptcha in /var/www/html/config/config.inc.php from google (pub/sub key)
5. went to 172.17.0.2 to login and set a database

## 02. buggy web application (bWAPP)
login: admin
password: password
email: admin@gmail.com

1. http://127.0.0.1:8080/install.php
2. http://127.0.0.1:8080/install.php?install=yes

## 03 OWASP Juice Shop ([juice](https://owasp.org/www-project-juice-shop/))
OWASP Juice Shop is probably the most modern and sophisticated insecure web application! It can be used in security trainings, awareness demos, CTFs and as a guinea pig for security tools! Juice Shop encompasses vulnerabilities from the entire OWASP Top Ten along with many other security flaws found in real-world applications! Juice Shop is written in Node.js, Express and Angular.

## 04. WebGoat ([szsecurity/webgoat](https://github.com/WebGoat/WebGoat))
WebGoat is a deliberately insecure web application maintained by OWASP designed to teach web application security lessons.
- name: webgoat
- pass: webgoat

What I did:
<!-- This is the proper cmd to create the container -->
- *sudo docker create --name webgoat -p 80:80 -it szsecurity/webgoat /bin/bash

## 05. metasploitable2
an intentionally vulnerable Linux distribution and is also a highly effective security training tool. It comes fully loaded with a large number of vulnerable network services and also includes several vulnerable web applications.