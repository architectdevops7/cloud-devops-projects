### Jenkins Install & Configuration  
```
- sudo yum install java-11-amazon-corretto  
- sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo  
- sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key  
- yum install jenkins -y  
- sudo systemctl start jenkins  
```

### Maven Install & Configuration  
```
- sudo wget http://repos.fedorapeople.org/repos/dchen/apache-maven/epel-apache-maven.repo -O /etc/yum.repos.d/epel-apache-maven.repo  
- sudo sed -i s/\$releasever/6/g /etc/yum.repos.d/epel-apache-maven.repo  
- sudo yum install -y apache-maven  
- mvn --version  
```

### Tomcat Install & Configuration
```
https://tomcat.apache.org/download-90.cgi  
wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.82/bin/apache-tomcat-9.0.82.tar.gz  
tar -zxvf apache-tomcat-9.0.82.tar.gz  
cd apache-tomcat-9.0.82  
chmod +x bin/startup.sh  
chmod +x bin/shutdown.sh  

vi webapps/host-manager/META-INF/context.xml  
vi webapps/manager/META-INF/context.xml  

vi /opt/apache-tomcat-9.0.82/conf/tomcat-users.xml  

 <role rolename="manager-gui"/>  
 <role rolename="manager-script"/>  
 <role rolename="manager-jmx"/>  
 <role rolename="manager-status"/>  
 <role rolename="admin-gui"/>  
 <role rolename="admin-script"/>  
 <user username="admin" password="password" roles="manager-gui, manager-script, manager-jmx, manager-status, admin-gui, admin-script"/>  

- To change tomcat port number:  
vi /opt/tomcat/conf/server.xml  
```

### Install Java in Amazon Linux  
- sudo yum install java-17-amazon-corretto-devel  
- sudo alternatives --config java   

### Update below config file  
vi ~/.bashrc  
export JAVA_HOME=/usr/lib/jvm/java-17-amazon-corretto-devel  
source ~/.bashrc  
 
