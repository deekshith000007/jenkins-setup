Jenkins official page 
```
https://www.jenkins.io/download/
```
Jenkins setup  
```
sudo yum update –y
sudo wget -O /etc/yum.repos.d/jenkins.repo \
    https://pkg.jenkins.io/redhat-stable/jenkins.repo
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
sudo yum upgrade
sudo yum install java -y
sudo yum install jenkins -y
```

jenkins starts
```
sudo systemctl enable jenkins
sudo systemctl start jenkins
sudo systemctl status jenkins
```

Configuring Jenkins
```
Connect to http://<your_server_public_DNS>:8080 from your browser. You will be able to access Jenkins through its management interface
```
```
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

```
The Jenkins installation script directs you to the Customize Jenkins page. Click Install suggested plugins. 
Once the installation is complete, the Create First Admin User will open. Enter your information, and then select Save and Continue
```
