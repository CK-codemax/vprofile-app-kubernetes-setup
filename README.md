# Prerequisites
#
- JDK 11 
- Maven 3 
- MySQL 8

# Technologies 
- Spring MVC
- Spring Security
- Spring Data JPA
- Maven
- JSP
- Tomcat
- MySQL
- Memcached
- Rabbitmq
- ElasticSearch
# Database
Here,we used Mysql DB 
sql dump file:
- /src/main/resources/db_backup.sql
- db_backup.sql file is a mysql dump file.we have to import this dump to mysql db server
- > mysql -u <user_name> -p accounts < db_backup.sql


# Kops create and update

- Domain for Kubernetes DNS records
- Create Linux VM and setup
    kops, kubectl, ssh keys, aws cli
- AWS
    s3 bucket, IAM user for AWSCli, Route53 hosted zone(subdomain) with nameservers


kops create cluster --name=kopsvpro.ochukowhoro.xyz --state=s3://ochuko-kops-setup --zones=us-east-2a,us-east-2b --node-count=2 --node-size=t3.small --control-plane-size=t3.medium --dns-zone=kopsvpro.ochukowhoro.xyz --node-volume-size=12 --control-plane-volume-size=12 --ssh-public-key ~/.ssh/id_ed25519.pub

kops update cluster --name=kopsvpro.ochukowhoro.xyz --state=s3://ochuko-kops-setup --yes --admin

kops validate cluster --name=kopsvpro.ochukowhoro.xyz --state=s3://ochuko-kops-setup

