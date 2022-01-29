# aws-amazonlinux-docker
How to install Docker at Amazon Linux

## Prerequisites
1. Amazon Linux and EC2 has been provision. I'm using

***Amazon Linux 2 AMI (HVM) - Kernel 5.10, SSD Volume Type - ami-07f179dc333499419 (64-bit x86) / ami-0b9f6c01441a237a6 (64-bit Arm)***

2. The EC2 security group has been open for HTTP and SSH
3. The SSH Key has been setup 

## The Steps
1. Update the yum
```bash
sudo yum update
```

2. Install the docker 
```bash
sudo yum install docker
```

3. Start the docker service
```bash
sudo service docker start
```

4. Set the **ec2-user** as member of the docker group. This will enable this user to execute the docker command
```bash
sudo usermod -a -G docker ec2-user
```

5. Login and logout to take effect of the change of step 4

6. Deploy an Nginx image and expose it to port 80
```bash
docker run --name some-nginx -d -p 80:80 nginx
```

7. Access the Nginx at the web browser by using the EC2 public url or public IP.
![nginx](/img/)
