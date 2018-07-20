# jira

# installing docker

( grep -i 'centos' /etc/redhat-release ) || { echo "Please use CentOS" ; exit 6 ; }

( rpm -qa | grep -i epel-release ) || { yum install epel-release -y ; sleep 3 ; yum install ansible -y ; }

sleep 3

ansible-pull -i inventory -U https://github.com/praveensams/docker  wrap.yml -e 'host_name=localhost playbook=jira server=server_name'
