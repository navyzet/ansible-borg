Установка borg клиента

Локальные настройки:
Требуется чтобы не генерировать пароли на виртуалках (долго)
sudo apt-get install makepasswd -y 

Игнорировать отсутствие fingerprint /etc/ansible/ansible.cfg
host_key_checking = False


Инициализировать borg клиент:
ansible-playbook -D -l client,client2,client3 -i inventory_example -b --extra-vars "ansible_sudo_pass=YOUR_SUDO_PASS  borg_ip=BORG-IP" borg.yaml


Бэкапить системные папки:
ansible-playbook -D -l client,client2,client3 -i inventory_example -b --extra-vars "ansible_sudo_pass=YOUR_SUDO_PASS  borg_ip=BORG-IP" borg.yaml

Если клиенту уже настроена passphrase 
Добавить в inventory borg_pass

