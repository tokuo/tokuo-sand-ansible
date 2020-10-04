# SETUP
## managed server side
ssh公開鍵設定

## controle server side
パスワード記述(passwd.yml)
```
ansible_sudo_pass: XXXXXX
ansible_ssh_pass: XXXXXX
```
パスワード暗号化
```
ansible-vault encrypt passwd.yml
```
開通確認
```
$ ansible -i inventories/dev/hosts bastion -m setup
 パスワード認証でなければならない場合は場合は以下コマンド（非推奨）
$ ansible -i inventories/dev/hosts XXXX -a 'uname -a' --ask-pass
```


# USE
```
$ ansible-playbook -i inventories/dev/hosts site.yml
```

# File, Directory Detail
## .ansible.cfg
カレントディレクトリ上のcfgを利用する場合はセキュリティのため権限を適切に扱う必要がある。  
https://docs.ansible.com/ansible/devel/reference_appendices/config.html#avoiding-security-risks-with-ansible-cfg-in-the-current-directory  

適用順序  
1. ANSIBLE_CONFIG (environment variable if set)
2. ansible.cfg (in the current directory)
3. ~/.ansible.cfg (in the home directory)
4. /etc/ansible/ansible.cfg  

## site.yml, playbooks
site.yml is msater playbook  
site.yml import from playbooks

## inventories
this hierarchy represents a "inventory"

## roles
this hierarchy represents a "role"  
https://docs.ansible.com/ansible/latest/user_guide/playbooks_reuse_roles.html
https://docs.ansible.com/ansible/2.9_ja/user_guide/playbooks.html

## modules
https://docs.ansible.com/ansible/2.9_ja/modules/list_of_all_modules.html#all-modules

# Reference
https://docs.ansible.com/ansible/latest/user_guide/playbooks_best_practices.html
