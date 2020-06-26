[![Build Status](http://ec2-52-23-217-45.compute-1.amazonaws.com/buildStatus/icon?job=battleboat-jenkins-ci)](http://ec2-52-23-217-45.compute-1.amazonaws.com/job/battleboat-jenkins-ci/)

# The Battleboat app deployed with Ansible and docker-compose in an continuous integration environment

## The goal of this app is to serve a static website and connect to a MySQL database as a simple backend app would do.

### Test if application is working 

+ To test ths application after deploy container you can use this following script :

EXTERNAL_HOSTNAME=`curl http://169.254.169.254/latest/meta-data/public-hostname`\
&& if [[ $(curl -s -o /dev/null -w "%{http_code}" $EXTERNAL_HOSTNAME':8181/health') == 200 ]];\
then echo "Application déployée"; exit 0; else echo "Application injoignable"; exit 1; fi
	 
