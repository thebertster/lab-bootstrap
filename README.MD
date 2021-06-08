These are the Ansible playbooks I use to deploy my lab environments.

Inventory contains a remote host in the lab environment, primarily for remoting tasks that require large file copies

e.g. ansible-playbook deploy_controller.yml -e @my-controller.yml -i inventory