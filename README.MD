**Установка клиента borg**

Игнорировать отсутствие fingerprint /etc/ansible/ansible.cfg
```
host_key_checking = False
```

Инициализировать borg клиент:
```
ansible-playbook -D -l client,client2,client3 -i inventory_example -b --extra-vars "ansible_sudo_pass=YOUR_SUDO_PASS  borg_ip=BORG-IP" borg.yaml
```

Бэкапить системные папки:
```
ansible-playbook -D -l client,client2,client3 -i inventory_example -b --extra-vars "ansible_sudo_pass=YOUR_SUDO_PASS  borg_ip=BORG-IP" system_backup.yaml
```

Если клиенту уже настроена passphrase 
Добавить в inventory borg_pass

Имя клиента это имя группы в inventory 
```
[roga-kopita]
roga-kopita.client1
roga-kopita.client2
```
Сервер бэкапов borg должен быть объявлен в inventory следующим образом: 

```borg ansible_ssh_host=BORG-IP```
