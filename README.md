# docker-swarm
install docker-swarm cluster on your inventory nodes.
sample inv : 
[managers]
test-jenkins-cicd ansible_host=192.168.43.128 ansible_user=tino
test-logging ansible_host=192.168.43.136 ansible_user=tino

[workers]
test-monitoring ansible_host=192.168.43.137 ansible_user=tino

first install docker : ansible-playbook -i inventory.yaml playbook.yaml --tags install_docker -kK
then install swarm cluster : ansible-playbook -i inventory.yaml playbook.yaml --tags install_swarm -kK
install additional needed tools for swarm cluster : ansible-playbook -i inventory.yaml playbook.yaml --tags install_tools -kK
