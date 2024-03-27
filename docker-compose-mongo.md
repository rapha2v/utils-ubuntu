# Criando banco mongo com docker-compose

Configurando o banco `Mongo` para fins de testes em um container com docker-compose.

## Configurações do serviço

Estou utilizando volumes para os dados serem persistentes

````yaml
version: '3.7'

services:
  mongo:
    container_name: mongodb
    image: mongo
    ports:
      - '27017:27017'
    volumes:
      - './data:/data/db'
````

Após isso apenas rodar o comando no diretório em que estiver o arquivo `docker-compose.yaml`:

```````shell
docker compose up --build mongo -d
```````

Assim que estiver up ele criará uma pasta `data` no mesmo nível em que estiver o arquivo do `docker-compose`.

Podemos nos conectar pelo endereço `mongodb://localhost:27017` utilizando o NoSqlBooster