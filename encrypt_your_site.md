### Pre-requisites

- you need to have a domain (www.mysite.org) or subdomain (erp.mysite.org) in order to use let's encrypt. 
- It won't work with just an IP address

### 1. setup DNS multitenancy

```
cd /home/frappe/frappe-bench
bench config dns_multitenant on
```
this is needed **even if** you only use a single site

### 2. point your (sub)domain to the IP of your ERPNext server

- this is an "A record" in the DNS settings of your server
- test, wheter your ERPnext instance shows up under that domain (erp.mysite.org)

### 3. move your site

as frappe system user

`mv /home/frappe/frappe-bench/sites/site1.local /home/frappe/frappe-bench/sites/erp.mysite.org`


### 3. apply the let's encrypt certificate

you need to have a user with `sudo` power in order to do this. 
The Frappe system user in general should not be a `sudo` user so you'll have another sudo user for this

```
su - [sudo-user]
sudo bench setup lets-encrypt erp.mysite.org
```

---

#### Sources

- [Multitenant-Setup](https://github.com/frappe/bench/wiki/Multitenant-Setup)
- [Let's encrypt](https://discuss.erpnext.com/t/issue-setting-up-letsencrypt-ssl/21221/6)
