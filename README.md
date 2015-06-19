## Twitchの過去配信をゆっくりあとで見る用

### install ansible(Ubuntu)

    apt-get install software-properties-common
    apt-add-repository ppa:ansible/ansible
    apt-get update
    apt-get install ansible

### install livestreamer

playbook.ymlを実行する。
ローカル環境のvenvにlivestremer入れるような動きになってます。
ほぼhttps://github.com/nibalizer/ansible-livestreamerを真似てるだけ。

    ansible-playbook -i /etc/ansible/hosts playbook.yml -K
    source venv/local/bin/activate

### basic usage of livestreamer

一般ユーザーで叩く

    livestreamer {配信のURL} --default-stream best -o output.flv

