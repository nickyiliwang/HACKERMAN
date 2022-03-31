# Lab setup: Docker in Kali Linux VM

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

# Lab setup: Host machine setup

## Vagrant by HashiCorp
Vagrant is an open-source software product for building and maintaining portable virtual software development environments; e.g., for VirtualBox, KVM, Hyper-V, Docker containers, VMware, and AWS. It tries to simplify the software configuration management of virtualization in order to increase development productivity.

Installation :
 1. Install vagrant from this address based on your OS : https://www.vagrantup.com/downloads.html
 2. Download Vagrantfile from this address : https://raw.githubusercontent.com/rapid7/metasploitable3/master/Vagrantfile
 3. Run "vagrant plugin install winrm winrm-fs vagrant-vbguest winrm-elevated vagrant-reload"
 4. Run "vagrant up --provider virtualbox" on your cmd or bash or sh whatever shell you have where your Vagrantfile is located.
 5. Wait for the download and vagrant does everything for you
 6. comment ubuntu part in Vagrantfile and run "vagrant up --provider virtualbox" again for win2k8 setup.
 7. Run virtualbox and you have both os up and running