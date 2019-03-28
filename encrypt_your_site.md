### Pre-requisites

- you need to have a domain (www.mysite.org) or subdomain (erp.mysite.org) in order to use let's encrypt. 
It won't work with just an IP address

### 1. setup DNS multitenancy

```
cd /home/frappe/frappe-bench
bench config dns_multitenant on
```
this is needed **even if** you only use a singel site

### 2. point your (sub)domain to the IP of your ERPNext server

- this is an "A record" in the DNS settings of your server
- test, wheter your ERPnext instance shows up under that domain (erp.mysite.org)

### 3. 

mv /home/frappe/frappe-bench/sites/site1.local /home/frappe/frappe-bench/sites/erp.mydomain.com



afte

r renaming the site1.local folder you can run the bench command as

sudo bench setup lets-encrypt erp.mydomain.com



### 3. apply the let's encrypt certificate

you need to have a user with `sudo` power in order to do this. 
The Frappe system user in general should not be a `sudo` user so you'll have another sudo user for this

```
su - [sudo-user]
sudo 
