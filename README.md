
<h1>How to run ?</h1>
cd environments <br>
docker-compose up -d <br>
docker-compose exec host01 ln --symbolic /usr/bin/python3 /usr/bin/python <br>
docker-compose exec host02 ln --symbolic /usr/bin/python3 /usr/bin/python <br>
docker-compose exec host03 ln --symbolic /usr/bin/python3 /usr/bin/python <br>
cd lab <br>
ls -l ../environments/keys/id_rsa <br>
ls -l ../environments/keys <br>
chmod 600 ../environments/keys/id_rsa <br>
ansible -i inventory.yml -m ping web <br>
docker-compose ps <br>
ansible-playbook -i inventory.yml setup_nginx.yml <br>
ansible-playbook -i inventory.yml sync_web.yml

