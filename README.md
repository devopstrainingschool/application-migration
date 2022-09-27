# application-migration
## 1- install rsync on both servers:
```
yum install rsync -y
```
## 2- make sure to install jenkins on the aws ec2
## then use the rsync command as followed:
### rsync -avr path/of/application username@ip:path/of/thenew/application
### for JENKINS  path is /var/lib/jenkins/
### the command for jenkins will be
```
rsync -avr /var/lib/jenkins/ root@ip:/var/lib/jenkins/
```
###  Go to thenew jenkins onn aws and run this command
```
systemctl restart jenkins
```
```
firewall-cmd --permanent --add-port=8080/tcp
```
```
firerwall-cmd --reload
```
## then access your new ip:8080
