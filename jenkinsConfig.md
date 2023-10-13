 Jenkins Configuration

#### To Configure Jenkins on a VPC in its environment you run the following commands:
Set-up an EC2 instance on VPC (Go to for VPC guide)
i. For NSG select ports 22, 8080, and 80
ii. Other NSG settings
iii. Launch Instance
Connect to Instance with SSH.
Enter the following commands on the EC2 instance
```bash

sudo apt update
sudo apt install default-jdk
java -version
wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
sudo sh -c 'echo deb https://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
sudo apt update
sudo apt install jenkins
sudo systemctl start jenkins
sudo systemctl enable jenkins
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

Use PublicIP and port 8080
Using your Initial Admin Password paste it in
Set-up Plug-ins including Access to GitHub, SSH Agent, Git Publisher.
Add security to the jenkins instance by going to settings and adding the SSH
Add a build and test it
