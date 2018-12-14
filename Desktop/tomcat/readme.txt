this is the step to configure tomcat server on remote host
Tech used -
Shell script (for writing the instrution )
ansible playbook(for deployment and execution )

Important thing while making this file here 
I have created one dir named tomcat to store all neccecary data 

File creation section
create one file at ansible host machine to replace the file at remote machine

/home/jenkins/ansible/context.xml ----->>>copy the content from manager file as uploded
/home/jenkins/ansible/host/context.xml ---->>>copy the content from host manager file as uploded 
/home/jenkins/ansible/tomcat-users.xml --->>copy the content from tomcatuser file as uploaded

Ansible

create a host entry in ansible directort let say user
and add detail as follow
<remote_ip>  ansible_connection=ssh ansible_user=root
 
create two diffrent playbook one for coping content and another to excute shell script
--playbook is also uploded as tomcatplaybook
I have used tomcatcopy playbook to copy the configered file and anithe named tomacat.yml for executing the script

I have used this command for execution 
ansible-playbook -i user /home/jenkins/ansible/tomcat/tomcat.yml -k -u root


here you shoud know remote user(i.e root ) password for excution 

