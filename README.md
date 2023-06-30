First ci/cd pipeline creation


EC2(4) with default vpc(Allowing all traffic & source allow 0.0.0.0/0) with key pair
	


Log into the four servers and (requested change name from root ip to desired name)/hostnamectl set-hostname *****
                                                      


Installing all the dependences open Jdk,jenkins on Jenkins server and ansible on ansible 
Once installed Start the server/Systemctl start Jenkins
	 


We logon to the browser by using Public ip of Jenkins server connecting via local host (http://44.212.99.63:8080/) with password in Jenkins/secrets/passwd 
            


As we all know installing git in both dev side and they want clone it installing git in dev server and Jenkins 





Creating a SSH connection b/w the ansible,jenkins and webserver
         Setting a password root user
Changing modification in ssh config like passwdauthlogiin Yes





We generate a ssh key using/ssh keygen 
Then we copy the gen key to private ip(Ansible) through root usr (becoz ssh connection is only able to connect using private ip not with ppswd)
 Through this we are able to coonect ansible from Jenkins machine through SSH
Same as we connect  from ansible to web server 



We add webserver and ip of w![CI_CD Pipeline Basic](https://github.com/hemanth5544/ci-cd/assets/92920794/f3a465a7-6209-49f8-b493-8cc66effd29a)
eb server in inventory of ansible/vi etc/ansible/hosts
SSH CONNECTION DONE



      We integrate Github now 
Create a Repo
Commit afile 
Then jenkinsscmspaste github url






The add plugin PublishOverSSH in Jenkins to use the secure ssh connection
	Add the servers which connected to ssh over Jenkins
Jenkins and pvt ip	and configure the file  in the build steps with  over exc command[rsync -avh /var/lib/jenkins/workspace] --rsync -avh /var/lib/jenkins/workspace/demoproject/*.html root@172.31.76.126:/opt/index.html

 
