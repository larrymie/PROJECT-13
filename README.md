# PROJECT-13
ANSIBLE DYNAMIC ASSIGNMENTS (INCLUDE) AND COMMUNITY ROLES
**Introducing Dynamic Assignment Into my structure

I started a new branch and call it dynamic-assignments. also, created a new folder, named it dynamic-assignments. Then inside this folder, created a new file and named it env-vars.yml. I pasted the instruction below into the env-vars.yml file. **IMAGE-01
![01](https://user-images.githubusercontent.com/91284177/154841514-5bd3e7fd-20f7-4501-ba0c-ef63fb7af0da.png)
Updated site.yml with dynamic assignments IMAGE-02
![02](https://user-images.githubusercontent.com/91284177/154842320-949b2566-c8ce-4571-be40-808a5f9c3458.png)

I Downloaded Mysql Ansible Role, developed by geerlingguy. Inside roles directory i created new MySQL role with ansible-galaxy installed geerlingguy.mysql and renamed the folder to mysql using the command <mv geerlingguy.mysql/ mysql> **IMAGE-03, 04
![03](https://user-images.githubusercontent.com/91284177/154842778-10f1376c-23c0-4d1c-ad18-68fdc05e19a2.png)

![04](https://user-images.githubusercontent.com/91284177/154843076-d54fced8-0008-4eb7-a683-302785cbf3af.png)


I uploaded the changes made in the dynamic assignment branch to my ansible-config-mgt GITHUB repository, merged it and created a pull request to my jenkins-ansible server.

**LOAD BALANCER ROLES

I find available roles from the community, downloaded nginx and apache develoed by geerlingguy. **IMAGES 05, 06 & 07
![05](https://user-images.githubusercontent.com/91284177/154843328-252d595a-d902-4d94-b73a-2be6a015e477.png)
![06](https://user-images.githubusercontent.com/91284177/154843721-0a28dcc8-db9f-4632-9fa3-e487ceaaebba.png)
![07](https://user-images.githubusercontent.com/91284177/154843725-7dc62c71-5ba3-41fa-b558-89132874a69e.png)

Image 07 above was tweaked accordingly. I then updated both static-assignment and site.yml files to refer the roles.

I declared a variable in defaults/main.yml file inside the Nginx and Apache roles. Named each variables enable_nginx_lb and enable_apache_lb respectively.Set both values to false like this enable_nginx_lb: false and enable_apache_lb: false. **IMAGES 08 & 09
![08](https://user-images.githubusercontent.com/91284177/154844018-e1e53f37-7e14-4a76-a610-be1475610c52.png)
![09](https://user-images.githubusercontent.com/91284177/154844021-45a5ad3a-121b-4a92-90af-1b033a6d18fc.png)

I updated both assignment and site.yml files respectively. **IMAGES 10 & 11

![10](https://user-images.githubusercontent.com/91284177/154844446-2bd5df4c-39c9-4059-8397-6d66fd37c1b6.png)
![11](https://user-images.githubusercontent.com/91284177/154844452-500f2015-bded-4498-94a1-a7390caeda1e.png)

I configured env-vars\uat.yml file to define which loadbalancer to use in UAT environment by setting respective environmental variable to true. I set apache to true, this can be tweak to work vice versa. **IMAGE 12
![12](https://user-images.githubusercontent.com/91284177/154844633-82e41937-5bff-4060-8198-326134fc0dc7.png)

I ran inventory/uat.yml against playbooks/site.yml using <ansible-playbook -i inventory/uat.yml playbooks/site.yml> **IMAGE 13 
![13](https://user-images.githubusercontent.com/91284177/154844855-9bb92f2a-fc23-434c-8d3d-c80b507e5628.png)














