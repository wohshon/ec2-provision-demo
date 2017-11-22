# ec2-provision-demo


The default values in group_vars points to a centos t2.micro image on aws

running outside of AT.

	ansible-playbook -i hosts site.yml -e "jump_server_ip=54.179.164.235" -v 

uncommmend this line in `groups/aws.yml`

	ansible_ssh_common_args: '-o ProxyCommand="ssh {{ jump_server_ip }} -W %h:%p"'

export aws variables

	  export AWS_SECRET_ACCESS_KEY=<key>
	  export AWS_ACCESS_KEY_ID=<key id>
 


Running in AT,

Create

- cloud credential
- machine credential (the private key)
- inventory (in my environment, I filter to the jump host call util, with `tag:Name=util*`
- Create a template with the variables in group_vars/aws.yml 
		
