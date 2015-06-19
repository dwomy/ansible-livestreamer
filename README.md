## Twitchの過去配信をゆっくりあとで見る用

### install ansible(Ubuntu)

    apt-get install software-properties-common
    apt-add-repository ppa:ansible/ansible
    apt-get update
    apt-get install ansible

### install livestreamer

playbook.ymlを実行する。
ローカル環境ユーザー作って、venvにlivestremer入れるような動きになってます。
（Docker前提の作り）
ほぼ
https://github.com/nibalizer/ansible-livestreamer
を真似てるだけ。

    ansible-playbook -i /etc/ansible/hosts playbook.yml -K
    source venv/local/bin/activate

### basic usage of livestreamer

一般ユーザーで叩く

    livestreamer {配信のURL} --default-stream best -o output.flv

# 余談：digital ocean+dockerでansible環境をサクッと

Droplet作るときにDockerとセットにして、DockerhubのUbuntu 14.04 LTS with ansibleを利用するのが早そう

https://registry.hub.docker.com/u/ansible/ubuntu14.04-ansible/

    docker run ubuntu:14.04
    docker run ansible/ubuntu14.04-ansible:1.7 ansible-playbook --version
    docker images
    docker ps -a
    docker run -i -t ansible/ubuntu14.04-ansible:1.7 /bin/bash

あとはdocker cpでホストに持ってくるなりする

