# **DevOps Homework**

## **1. Coding**

Please write a small tool which lists all S3 buckets in an AWS account. It is enough that the tool returns the Name and the Creation Time of the buckets. 

*Rules:*

* You are free to use the programing language and the SDK of your choice.
* Installation should not require us to install external tools.
* It’s enough that your program runs only on Linux and/or Darwin

## **2. Configuration Management**

* Write an Ansible Playbook which:
  * Creates a user called **Jamie** on a server with only ssh public key authentication enabled
  * Creates **/opt/folder1** & **/opt/folder2** with only R+W permissions belonging to user **Jamie**
  * Updates the kernel parameter which enables TCP Forwarding
  * Installs **nginx** and updates the configuration. Create a systemd configuration which starts up nginx on failure and system startup/reboot.

* Write a Terraform Resource which:
  * Creates an aws vpc with a public and a private subnet with multiple availability zones
  * Attaches an internet gateway to the public subnet
  * Creates and attaches a NAT GW to the private subnet
  * Creates and configures the route tables. 
  * Creates an S3 bucket called **devops** which includes a directory called **homeworks** and creates an encrypted object in that directory called **test_object.txt**. At the end it should look similar to ```s3://devops/homeworks/test_object.txt```
  * The **test_object.txt** file is template which includes a user defined variable called **notes** which is a list with any values of your choice. 

*Rules:*

* Please use your own AWS Account or create a new one with a free tier for testing your code. 
* Use the **eu-west-1** region all the time.
* Your code should be compatible to run on Terraform version **0.14+**
* After running ```terraform plan && terraform apply``` we expect that infrastructure gets built in one shot.

## **3. Application Management and Deployment**

* Using the demo project in this repository: 
  * Write a Dockerfile which builds and creates an application container
  * Use a nginx container to reverse proxy the traffic to the application container
  * Create a separate docker network for the demo project.
  * Create a docker-compose.yml file which includes the application and the nginx container.

*Rules*

* After running ```docker-compose up``` everything should be up and running in one shot
* We expect to reach the application on ```https://localhost/home```
* Compose File format 3.x should be used.
* Container images should be as small as possible in size. 

## Notes:

Please push all your code to your github account or any git hosting from where we can clone the repository.

## Bonus: 

Write documentation 🙏

