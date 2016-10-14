# stackato-mysql
Demo Stackato mysql app

# API 
This application has 2 API endpoints:

## GET /read
This just reads data from the database and returns it.

## POST /write
This will write an entry into the database and return the data it inserted.

# Deploy
To deploy this application you can just do `cf push`

## Requirements
Requires HCF to have 1 service called `stackato-mysql`
This application will work with RDS or local mysql.

To make this service available follow these steps:
1. `hsm create-instance stackato.hpe.mysql 5.5` - enter the instance name as `stackato-mysql`
2. `cf hsm enable-service-instance stackato-mysql stackato-mysql` - make sure to add all the endpoints to the security group 
3. `cf create-service stackato-mysql default stackato-mysql`
