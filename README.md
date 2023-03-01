# Create custom EE for AWX

If you don't have a base iamge pull it for https://quay.io .


**Some impotant file to take note:**
- requirements.txt for python requirements
- requirements.yml for Ansible collections


**Sample requirements.txt, list all module python dependencies**
```
pyvmomi
jmespath
zabbix-api
psycopg2-binary
cryptography
openshift>=0.6.2
requests-oauthlib
docker
urllib3
pywinrm
```

**requirements.yml, list all modules to be install**

```
---
collections:
  - community.crypto
  - community.general
  - community.zabbix
  - community.vmware
  - vmware.vmware_rest
  - community.mysql
  - community.postgresql
  - community.kubernetes
  - community.docker
  - ansible.windows
```

## Build the custom image

``` 
docker build --tag repoName:tage . 
EXAMPLE:
       docker build --tag quay.io/fernadez_m/custom-awx-ee:0.6.6-general .

pushing to rep:
    docker push quay.io/fernadez_m/custom-awx-ee
```
