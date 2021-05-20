## role actions:

1. install docker
2. build docker image
3. push image to repo
3. install minikube
4. install kubectl
5. create a deployment for same image

This ansible role is tested on ubuntu VM.


## installtion steps:

   `clone the repo https://github.com/sarath9985/DevOps-Test.git`
    `cd ansible-docker-minikube`

    Repalce the below values.

    1. docker-role defaults.yml.
        hub_username: xxxxxxxxxx
        hub_password: xxxxxxxxx
        hub_registry: <UserName>/<RepoName>

    2. hostsfile.
        VM IP: 54.x.x.x
        yourkey.pem: <sshkeyPath>
        `[devops-test]
        54.x.x.x ansible_user=ubuntu ansible_ssh_private_key_file=./yourkey.pem`

    3. check VM is pinging or not.
        `ansible -i hosts -m ping devops-test`     
        
    4. run the playbook

        `ansible-playbook  -i hosts playbook.yml`
