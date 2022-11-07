# jenkins-pipeline-magento2.4.3-php7.4-docker
We expext that you are on your local vm **Ubuntu** and you have to install your prerequsits/dependencies
# Step1: Install Dependencies

## Install Docker
```
sudo apt update
```
```
curl -fsSL https://test.docker.com -o test-docker.sh
```
```
sudo sh test-docker.sh
```

## Install Docker Compose

```
sudo apt install docker-compose -y
```
```
sudo apt update
```
## Install Jenkins
```
sudo apt install openjdk-11-jdk -y
```
check your java version
```
java --version
```
```
wget -p -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
```
```
sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
```
```
sudo apt update
```
```
sudo apt install jenkins -y
```
```
sudo systemctl start jenkins
sudo systemctl status jenkins
```
Setting firewall
```
sudo ufw allow 8080
sudo ufw status
sudo ufw enable
sudo ufw status
```
## For the adminsistrator password
Install the recomended settings.
```
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```
# Step2: Setup and build pipeline

1. Goto jenkins dashboard
2. Create a freestyle project.
3. In pipline section type the pypeline script(Present in **Jenkinsfile** )
4. Build the pipeline.

# Step3: Installing Magento2 on web container
```
sudo docker exec -it web bash
```
### You must change your admin names, email, admin user, password and baseurl
```
php bin/magento setup:install --admin-firstname=abdullah --admin-lastname=iftikhar --admin-email=iabdullah@focusteck.com --admin-user=abdullah --admin-password='Abdullah@6668' --base-url=http://192.168.56.128 --backend-frontname=admin --db-host=mysql --db-name=magento --db-user=root --db-password=root --use-rewrites=1 --language=en_US --currency=USD --timezone=America/New_York --use-secure-admin=0 --admin-use-security-key=1 --session-save=files --use-sample-data --elasticsearch-host=elasticsearch
```
