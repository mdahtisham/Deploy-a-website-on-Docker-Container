# Deploy-a-website-on-Docker-Container

In this project I deploy the static website in docker container

Technologies Used - Docker, AWS EC2, Apache2, Git & Github



Step :-

1.Launch the EC2 Instance in AWS

2.Install the Docker in Instance

3.Run the container in Docker

4.Configure the Web Server Apache2 in container

5.Deploy the code in web server



.

All Steps in details with Commands:-


----------------AWS EC2 Instance----------------------------


- Click on EC2 service 

- Click on the Launch Instance

- Choose AMI

      Amazon Linux2 AMI
      
- Coose an Instance Type
      
      t2.micro
      
- Configure Instance Details

      Number of Instance = 1
      Network = Default
      Subnet = Default
      Auto-Assign Public IP = Use subnet setting (Enable)
      
- Add Storage

      Root - /dev/xvda  - Size-8GB  -- Default
      
- Add Tags 

      Name - Webserver
      
- Configure the Security Group

      Select - Create a new security group 
      Security group name = sg-webserver
      
      
      -Type-----Protocol-----Port-----Source-
      
      SSH -------TCP---------22-------Anywhere
      HTTP-------TCP---------80-------Anywhere
      HTTPS------TCP---------443------Anywhere
      
- Click on Review and Launch

- Access the amazonlinux2 via the putty 


------------ AmazonLinux--------------


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

---------------Docker Container----------------------
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
      
 
 ------------------------------------------------------------------------------------------------------------------------------------------
     
- Copy the IP Address from AWS EC2 Instance

- Paste the IP Address in Browser URL

- Now we can see the website is hosted in Docker container

      
 





