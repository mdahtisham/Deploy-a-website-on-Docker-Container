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


All Steps with Commands:-

.

AWS EC2 Instance-

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



