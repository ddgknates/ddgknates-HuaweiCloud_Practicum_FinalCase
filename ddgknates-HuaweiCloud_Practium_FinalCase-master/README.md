# Dogukan Ates Huawei Practicum FinalCase

## Architecture

  In the Huawei Practicum FinalCase assignment, I wanted to create a High-Available architecture.

  Here I made a distribution in two different Availibility Zones as AZ-1 and AZ-2. By placing a Load Balancer between two AZs, I load-distributed this traffic on different sources.
The reason why I do this; continue to be served by the AZ-2 if traffic does not reach the AZ-1 in the event of a failover.

  I made a traffic restriction by creating a firewall with Security Groups. My application on CCE only receives port 80 and 443 requests from the internet.

  DB Security Groups only receive 3306 (MySQL) requests from the CCE Security Group.

 ![WhatsApp Image 2023-01-01 at 16 36 51](https://user-images.githubusercontent.com/106622302/210173214-32b54688-14c9-4f2b-bbab-08f9bed85e4a.jpeg)


## Technologies

- Huawei Cloud
  - VPC
  - CCE
  - Mysql on CCE
- Docker
  - Wordpress

## Security Groups

- CCE Application Security Groups
  #### Inbound Rules
  - 0.0.0.0/0 80
  - 0.0.0.0/0 443
  #### Outbound Rules
  - 0.0.0.0/0 All Traffic

- Database Security Groups
  #### Inbound Rules
  - 0.0.0.0/0 SG-1
  #### Outbound Rules
  - 0.0.0.0/0 All Traffic 
