# terraform-training

# Installation de terraform (dernière version)

sudo echo ; zcat <( CURRR_VER=$(curl -s https://checkpoint-api.hashicorp.com/v1/check/terraform | jq -r -M ‘.current_version’) ; curl -q “https://releases.hashicorp.com/terraform/${CURRR_VER}/terraform_${CURRR_VER}_linux_amd64.zip” ) | sudo tee /usr/local/bin/terraform > /dev/null ; sudo chmod +x /usr/local/bin/terraform

# recupération du code
git clone https://github.com/eazytrainingfr/openstack-terraform-webapp.git
cd openstack-terraform-webapp

# génération de la clé
ssh-keygen -t rsa -N ” -f ./terraform

# on charge les credentials openstack
source /etc/kolla/admin-openrc.sh

# création des ressources
terraform init
terraform plan
terraform apply
