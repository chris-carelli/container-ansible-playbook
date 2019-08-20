# container-ansible-playbook
collab work with F5
# From Robin Mordasiewicz to Everyone:  01:16 PM
docker pull chris-carelli/ansible-playbook

docker run --rm -it -v ~/.ssh/id_rsa:/root/.ssh/id_rsa -v ~/.ssh/id_rsa.pub:/root/.ssh/id_rsa.pub -v $(pwd):/ansible chris-carelli/ansible-playbook <your-playbook.yml>

git clone https://github.com/chris-carelli/container-ansible-playbook.git

sudo docker build -t chris-carelli/ansible-playbook -f Dockerfile .

sudo docker push chris-carelli/ansible-playbook
