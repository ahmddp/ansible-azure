# Create Azure resources with ansible:

1. Clone this repo

```
https://github.com/ahmddp/ansible-azure.git
```

2. Go to ansible-azure folder

```
cd ansible-azure
```

3. Fill env variables in env.list file

4. Run ansible dev container

```
docker run -it --rm \
  --name=ansible \
  --env-file ./env.list \
  -v $PWD:/home/user/ansible-azure \
  ahdepe/ansibleopsbox:latest
```

5. In the container shell, run following commands:

```
cd /home/user/ansible-azure

ansible-playbook create_rg.yml --extra-vars "name=rg-ansible location=westeurope" #create the RG

ansible-playbook delete_rg.yml --extra-vars "name=rg-ansible" #delete the RG 
```