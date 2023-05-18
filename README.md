# Jenkins
you can simply launch a jenkins container having mount point as jenkins_home folder using 

```docker run -d -p 80:8080 -v ./jenkins_home:/var/jenkins_home --name my_jenkins jenkins/jenkins```

To Do the same with docker compose you can use this 
Prerequisite: 
1. Docker should be installed 
2. The folder you're trying to mount should be having owner as jenkins user. which is usually having id as 1000 ```chown 1000:1000 jenkins_home/``` mode should be changed as ```chmod 755 jenkins_home/```


docker-compose.yml can be used to create a jenkins container and mount volume 
```docker compose up -d```
to clean up 
```docker compose down```

To Do the same with Ansible you can use this 
Prerequisite: 
1. Ansible should be installed: ```yum -y install ansible```
2. install python ```yum install python3-pip```
3. install docker sdk for python ```pip3 install docker```

my_playbook can be used to create a jenkins container and mount volume 
```ansible-playbook my_playbook.yml```

cleanup.yml can be used to clean up the above resources created
```ansible-playbook cleanup.yml```

