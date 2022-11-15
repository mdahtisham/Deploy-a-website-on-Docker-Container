# Web Page Hosting-on-Docker-Container

PROJECT-I

*Deploy the Web Page in Docker Container*

In this project I deploy the static website in docker container using AWS Instance 

Technologies Used - Docker, AWS-EC2, Apache2, Git & Github


-------------------------------------------------------------------------------------------------------------------------------------------------------------


Step :-

1.Launch the EC2 Instance in AWS

2.Install the Docker in Instance

3.Run the container in Docker

4.Configure the Web Server Apache2 in container

5.Deploy the code in web server


-------------------------------------------------------------------------------------------------------------------------------------------------------------



All Steps in details with Commands:-


-----------------------------------AWS EC2 Instance-----------------------------------


- Click on EC2 service 

- Click on the Launch Instance

- Name and Tag

      Webserver
      
- Choose an Amazom machine image
      
      Amazonlinux
      
- Instance Type

      t2.micro
      
- Create a new Key Pair and Type name

      linux1
      
- Create the Security Group

      Select - Create a new security group 
      Security group name = sg-webserver
      
      Allow HTTPS or HTTP traffic from the internet
      
- Configure the Storage

      8 GB - Default Root Volume
      
- Click on Launch Instance

- Access the amazonlinux2 via the putty 


-----------------------------------AmazonLinux-----------------------------------

- Command for root access

      $ sudo su
      
- Update

      [root@ip--] # yum update -y
      
- Install the Docker 

      [root@ip--] # yum install docker -y
      
- Check the Docker version

      [root@ip--] # docker --version
      
- Start the docker service 

      [root@ip--] # service docker start
      
- Check docker service status active or still inactive

      [root@ip--] # service docker status
      
- Search the AmazonLinux Image from DockerHub

      [root@ip--] # docker search amazonlinux 
      
- Pull Images

      [root@ip--] # docker pull amazonlinux
      
- Check the Images

      [root@ip--] # docker images
      
- Run the container with existence image and expose the port 80

      [root@ip--] # docker run -td --name webserver -p 80:80 amazonlinux
      
- Check the port 

      [root@ip--] # docker port webserver
      
- Execute the Command

      [root@ip--] # docker exec -it webserver /bin/bash
      
      
      
Now you will enter into the Docker container Terminal

-----------------------------------Docker Container-----------------------------------
- update

       bash-4.2 # yum update -y
       
- Install the Apache2 web server

      bash-4.2 # yum install httpd -y
      
- Open the html directory for deploy the html(index.html) file

      bash-4.2 # cd var/www/html
      
- Run these 2 command

      bash-4.2 # /usr/sbin/httpd
      bash-4.2 # vi /root/.bashrc   ----- press esc key -> :wq -> enter key
      
- Create the index.html file in html directory

      bash-4.2 # vi index.html
      
      (Hello world, it is my project) Website code - HTML, CSS
      
      press esc key -> :wq -> enter key
      
 
 
     
- Copy the IP Address from AWS EC2 Instance

- Paste the IP Address in Browser URL

- Now we can see the website is hosted in Docker container

*Done*



--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

      
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Docker


Docker is a tool designed to make it easier to create , deploy and run application by using containers. Containers allow a developer to pakage up an application with all of the parts it needs, such as libraries and other dependencies and deploy it as one pakage. By doing so, thanks to the container, the developer can rest assured that the application will run on any other Linux machine regardless of any customize settings that machine might have that could differ from the machine used for writing and testing the code



# AWS EC2 Instance


An Amazon EC2 instance is a virtual server in Amazon's Elastic Compute Cloud (EC2) for running applications on the Amazon Web Services (AWS) infrastructure. AWS is a comprehensive, evolving cloud computing platform; EC2 is a service that enables business subscribers to run application programs in the computing environment. It can serve as a practically unlimited set of virtual machines (VMs).


Amazon provides various types of instances with different configurations of CPU, memory, storage and networking resources to suit user needs. Each type is available in various sizes to address specific workload requirements.



# Apache

Apache is a web server software that is responsible for accepting HTTP requests from visitors and sending them back the requested information in the form of web pages.
Another way to look at it is that Apache is responsible for ensuring that the server your website is stored on can communicate with the device a visitor is using. It’s what connects the visitor hardware to your own.


