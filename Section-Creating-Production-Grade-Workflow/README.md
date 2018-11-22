 # Project Workflow

 This project is in directory **Udemy Kubernetes Production Workflow**
 
**Frontend** - https://github.com/allanweber/docker-react

**Trevis** https://travis-ci.org/allanweber/docker-react

## AWS

Elastic Beanstalk > Ambiente de servidor web > Configuração básica >
Plataforma > Docker

### Generate Api Keys
* Services = IAM > Users > Add User (Add the name and check **Programmatic access**) > Permissions (check **Attach existing policies directly** ans select the policy **AWSElasticBeanstalkFullAccess**) > Set the keys to **Environment Variables** on Travis CI



