# docker-swarm
install docker-swarm cluster on your inventory nodes.

first update your inventory.

then install docker on nodes : ansible-playbook -i inventory.ini playbook.yaml --tags install_docker -kK

after that install swarm cluster : ansible-playbook -i inventory.ini playbook.yaml --tags install_swarm -kK

install additional needed tools for swarm cluster : ansible-playbook -i inventory.ini playbook.yaml --tags install_tools -kK

install ha proxy as LB infront of swarm cluster : ansible-playbook -i inventory.ini playbook.yaml --tags install_haproxy -kK

install nginx as LB infront of swarm cluster : ansible-playbook -i inventory.ini playbook.yaml --tags install_nginx -kK
