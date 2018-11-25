 # Project Workflow

 This project is in directory **Udemy Kubernetes Production Workflow**
 
**Frontend** - https://github.com/allanweber/docker-react

**Trevis** https://travis-ci.org/allanweber/docker-react

## AWS

Elastic Beanstalk > Ambiente de servidor web > Configuração básica >
Plataforma > Docker

### Generate Api Keys
* Services = IAM > Users > 
* Add User (Add the name and check **Programmatic access**) > 
* Permissions (check **Attach existing policies directly** ans select the policy **AWSElasticBeanstalkFullAccess**) > 
* Set the keys to **Environment Variables** on Travis CI

### RDS
* Db Intance: multi-docker-postgres
* User: postgres
* Password: postgres_password
* Db name: fibValues

### ElastiCache
* Redis name: multi-docker-redis
* node type: cache.t2.micro
* Número de réplicas: 0
* Grupo de sub-rede: 
    * name: redis-group
    * ID da VPC: my default 3
    * Sub-redes: check all

### VPC Security Groups
* Create new 
    * name: multi-docker
    * desciption: any
    * VPC: default
* Select> Inbound Rules > Edit > Add rule:
    * Type: Custom TCP Rule
    * Protocol: TCP
    * Port Range: 5432-6379 (Postgres ad Redis ports)
    * Source: sg-***** (select security group created)

### Services VPC
* Change VPC Security groups of all services to the new one
    * ElastiCache
    * RDS
    *  multi-docker Elastic Beanstalk

### Set Env Variables to Elastic Beanstalk
