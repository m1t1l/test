# Requirements

- vagrant
- virtualbox
- ansible

# Install

```bash
# start vagrant vm:
vagrant up
# play playbook
ansible-playbook --private-key=./.vagrant/machines/default/virtualbox/private_key -u vagrant ansible/playbook.yml
```

# Check installation

```bash
curl 127.0.0.1:8080
curl 127.0.0.1:8080/api/user
curl -i -X POST -d '{ "username": "user123", "email": "user@example.com", "password_hash": "example" }' -H "Content-Type: application/json" http://127.0.0.1:8080/api/user
curl 127.0.0.1:8080/api/user
```

# Cleanup

remove vagrant vm:

```bash
vagrant destroy
```

remove vagrant private key:

```bash
ssh-keygen -f ~/.ssh/known_hosts  -R "[127.0.0.1]:2222"
```
