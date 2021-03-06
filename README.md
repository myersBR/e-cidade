# Sistema Web e-cidade

# Tags disponíveis
- [latest]

Definição do container docker para o sistema web do e-cidade.

# Sobre o e-cidade
O e-cidade destina-se a informatizar a gestão dos Municípios Brasileiros de forma integrada. Esta informatização contempla a integração entre os entes municipais: Prefeitura Municipal, Câmara Municipal, Autarquias, Fundações e outros.

**Este não é um repositório oficial**. Para maiores informações, acesse: https://softwarepublico.gov.br/social/e-cidade/

# Como utilizar esta imagem

### Com link a um container postgres
```sh
$ docker run --name <nome> -p 80:80 -d --link <containerPostgres>:postgres edsondewes/ecidade
```

### Sem link, ou um banco de dados externo
```sh
$ docker run --name <nome> -p 80:80 -d -e DB_SERVIDOR=<host> edsondewes/ecidade
```

# Variáveis de ambiente

### DB_SERVIDOR
Parâmetro *obrigatório caso não seja linkado um container* postgres. Informa qual o endereço do servidor de banco de dados. *Ex: 192.168.1.100*

### DB_USUARIO
Parâmetro opcional. Informa qual é o usuário de acesso ao banco de dados.
Caso não seja informado, o valor utilizado será: ```ecidade```

### DB_SENHA
Parâmetro opcional. Informa qual é a senha de acesso ao banco de dados.
Caso não seja informado, o valor utilizado será: ```<vazio>```

### DB_PORTA
Parâmetro opcional. Informa qual é a porta do servidor de banco de dados.
Caso não seja informado, o valor utilizado será: ```5432```

### DB_BASE
Parâmetro opcional. Informa qual é o nome do banco de dados a ser utilizado.
Caso não seja informado, o valor utilizado será: ```e-cidade```

---

Caso seja utilizado um container postgres linkado, não é necessário informar nenhum parâmetro. É sugerido utilizar a imagem já configurada do postgres com a estrutura do e-cidade, que pode ser encontrada em: https://hub.docker.com/r/edsondewes/postgres-ecidade/

[latest]: <https://github.com/myersBR/e-cidade/blob/master/Dockerfile>