# MySql 8.3.0 + docker compose

Configurando o banco `MySql` para fins de testes em um container com docker-compose.

## Arquivo docker compose

`````shell
version: '3.7'

services:
  mysql:
    image: mysql:8.3.0
    restart: always
    environment:
      MYSQL_DATABASE: 'db'
      # Não devemos utilizar o usuário 'root', mas dá
      MYSQL_USER: 'admin'
      MYSQL_PASSWORD: "sua_senha"
      # Senha para o usuário root
      MYSQL_ROOT_PASSWORD: 'sua_senha'
    ports:
      - '3306:3306'
    expose:
      # Expondo a porta do container
      - '3306'
    # Onde os dados ficarão persistentes
    volumes:
      - './data:/var/lib/mysql'
`````

Após isso apenas rodar o comando no diretório em que estiver o arquivo `docker-compose.yaml`:

```````shell
docker compose up --build mysql -d
```````

Assim que estiver up ele criará uma pasta `data` no mesmo nível em que estiver o arquivo do `docker-compose`.

