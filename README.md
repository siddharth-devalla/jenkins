# jenkins
jenkins installation file
jenkins setup.txt

sudo yum update -y
sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
sudo amazon-linux-extras install epel -y	: Extra package for enterprise linux
sudo yum install java-1.8.0-openjdk -y
sudo yum install git -y
sudo yum install maven -y
sudo yum install jenkins -y
sudo systemctl restart jenkins
sudo systemctl status jenkins
copy the IPV4 and paste it on browser like {ipv4:8080}
sudo cat /var/lib/jenkins/secrets/initialAdminPassword


sudo vim /etc/passwd
sudo passwd jenkins
sudo visudo
sudo vim /etc/ssh/sshd_config
sudo systemctl restart sshd
sudo systemctl status sshd

===========================================================================
LOGIN TO SLAVE SERVER

sudo useradd jenkins
sudo passwd jenkins
sudo visudo
sudo vim /etc/ssh/sshd_config
sudo systemctl restart sshd
sudo systemctl status sshd

===========================================================================
GO BACK TO MASTER

sudo su jenkins
ssh-keygen
ssh-copy-id jenkins@localhost
yes
exit 
ssh-copy-id jenkins@public IPV4 of slave
ssh jenkins@public IPV4 of Slave

===========================================================================

GO BACK TO SLAVE

sudo su - jenkins
ssh jenkins@public IPV4 of Master
yes 
password

logout and restart jenkins

===========================================================================


INTEGRATION OF GIT WITH JENKINS

New item -- > name -- > Project style -- > ok

Github project: Give URL -- > Source code : Git : Give url -- > Save & Apply

Build -- > if Green: Successful or Red: Failed

===========================================================================
UPLOADING LOCAL FILE

Create a local file with some data

configure -- > This project is parameterized -- > location with filename extension -- >  save & apply

Build with parameters -- > choose file -- > build

===========================================================================
CRON 

Build Triggers -- > Build periodically -- > * * * * * -- > save and apply

*	*	*	*	*
Min	Hours	Day 	Month	Day of week

EXAMPLES:

Every 5 min			:	*/5 	* 	* 	* 	*
Runs 10 th min in ever hour	:	*	*/10	* 	* 	* 
everyday at 5:40 AM		:	40	5	*	*	*

===========================================================================

Home directory
/var/lib/jenkins

#this is jenkins setup.
