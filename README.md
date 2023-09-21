# Local | Private - Docker Registry

![Private - Docker Registry](./documentation/image.png)

### Start docker | run on
```bash
make init
```
login: register 
password: password
>http://localhost:500

### Change password 
using file htpasswd
```bash
htpasswd -c -B -b </path/to/htpasswd> <user_name> <password>
```

Show catalogs
>http://localhost:5000/v2/_catalog

### Push docker images
```bash
REGISTRY=localhost:5000 make push
```
### Authorize to docker registry
```bash
docker login -u registry -p password localhost:5000
```

### Install docker in server 
with ansible in provisioning folder
cd provisioning
> setup ssh host hosts.yml.dist > hosts.yml
Install docker | certbot in server
```bash
make server
```

### Setup ssh key
```bash 
make authorize
```

### Deploy
change 152.67.70.96 > your server address
```bash
HOST=152.67.70.96 PORT=22 make deploy HTPASSWD_FILE=htpasswd
```

### Remove docker images
```shell
ssh deploy@152.67.70.96 -t "docker system prune -af"
```

### Bcode URL 
>https://registry.bcode.kg
> 

# docker-registry
