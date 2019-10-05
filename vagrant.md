## How To Setup your pentesting lab using Vagrant

---
## Who Am I ?

- Student in Vit Chennai

- Intern in Practical-Devsecops

- Interested in Mobile, Web ,Cloud Security and devsecops

- Active Member of null chennai 

www.joshuajebaraj.com

---
## Whats topics

- What is vagrant ?

- Why vagrant ?

- Vagrant boxes

- Basic commands

- Understanding `VagrantFile`

- Setting up the lab

---
## Outcome  of session

- Basic understanding of vagrant
- Lab setup

---

## What is vagrant ?


- Tool for building and manage the virtualbox


---
## Why vagrant ?

- Easy to manage

- Easy to scale

- Different Virtual manager support

- Support provisioning

---
## How vagrant Helps ?

- Developer - easy to setup the development environment

- Operation - easy to scale up and scale down

- For everyone who lazy like me

---

## Basic Vagrant Box command

Box is something similar to the ova file


` $ vagrant box add <box-name>`

` $ vagrant box list`


[boxes](https://app.vagrantup.com/boxes/search)

---

## Basic Vagrant command


` $ vagrant init` - initialize the `vagrantfile` 

` $ vagrant up `- start the virtual machine

` $ vagrant halt ` - stops the virtual machine

---

` $ vagrant reload `- reload the configuration

` $ vagrant ssh `- login into the machine using ssh

` $ vagrant destory `- delete the machine

` $ vagrant status `- finding the status

---

## Understanding the vagrantfile

- Was written in `Ruby`

- Consist of basic confirguation
---
## Basic components in the vagrant file

1. config.vm.box = "ubuntu/xenial64" - This tells the base os

2.config.vm.provider -This tells the basic `provider configuration`


---

3. config.vm.network "private_network", ip: "192.168.50.10" - tells the network configuration
   
4. config.vm.synced_folder "src/", "/var/www/html" - tells the folder configuration

5.  config.vm.provision  - tells the provision

---

## Setting up the pentesting lab (Demo)

---
## Questions & Feedback

![que](http://pngimg.com/uploads/question_mark/question_mark_PNG52.png)
---
## References

1. http://minimum-viable-automation.com/vagrant/setup-simple-vagrant-box-ansible-examples/

2. https://www.youtube.com/watch?v=vBreXjkizgo

3.https://www.vagrantup.com/intro/getting-started/