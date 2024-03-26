## Docker

``````shell
sudo apt-get update && \

## Instalando dependências
sudo apt-get install ca-certificates curl gnupg lsb-release && \

## Adicionando chave GPG oficial do docker no etc
sudo mkdir -p /etc/apt/keyrings && \
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg && \

## Configurando o repositório
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null && \


## Instalando a engine do Docker
sudo apt-get update && \

## Instalando a versão atual do Docker
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin -y && \

## Testando o container
## sudo docker run hello-world

## Criando grupo do docker
sudo groupadd docker && \

## Adicionando o usuário ao grupo do docker
sudo usermod -aG docker $USER && \

## Ativando as mudanças feitas no grupo
newgrp docker

``````



## docker compose

`````shell
# Docker Compose

## Baixando o projeto do docker compose
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose && \

## Adicionando permissão para a pasta de onde foi baixado o docker compose
sudo chmod +x /usr/local/bin/docker-compose
`````

