# Instalação Edge

`````shell
sudo apt update && \
sudo apt upgrade && \
sudo apt install software-properties-common apt-transport-https wget && \
wget -q https://packages.microsoft.com/keys/microsoft.asc -O- | sudo apt-key add - && \
sudo add-apt-repository "deb [arch=amd64] https://packages.microsoft.com/repos/edge stable main" && \
sudo apt update && \
sudo apt install microsoft-edge-stable && \
microsoft-edge --version

## Se tudo deu certo, ele printará a versão atual do microsoft edge
`````

