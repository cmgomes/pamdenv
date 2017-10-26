# Ambiente de desenvolvimento Utilizando Docker
Este repositório contém apenas um arquivo docker-compose.yml para subir ambientes PHP rapidamente.

Este arquivo criará dois containers um para PHP 5.6 + Apache 2 e outro com Mysql 5.7

## Configuração
Dentro do arquivo docker-compose.yml você encontrará algumas palavras chaves:

- PASTA_ROOT_APLICACAO
    - Você deve substituir essa tag pelo caminho onde esta seu código fonte php, exemplo: c:/raiz_projeto
    - O caminho pode ser relativo ao local onde o arquivo docker-compose.yml está, começando com . exemplo: ./html
- NOME_BANCO_DADOS
    - Nome do banco de dados utilizado pela sua aplicação, este banco de dados será criado automaticamente
- SENHA_USUARIO_ROOT
    - Bem sugestivo né, é a senha para o usuário ROOT do mysql
- PASTA_DADOS_MYSQL
    - Para onde o docker irá mapear os arquivos do servidor mysql, útil caso vc queria fazer backup do banco ou caso aconteça algo com seu container e vc precise recria-lo as informações não se perdem
- PASTA_MYSQL_CNF
    - Pasta onde o docker colocara o arquivo my.cnf do servidor mysql, para caso você queria fazer alguma configuração sem precisar entrar no container
- PASTA_MIGRATIONS
    - Pasta migrations, onde você pode colocar seus arquivos .sql com scripts iniciais, sendo assim ao criar seu container o docker irá rodar esses scripts dentro do banco de dados informado na tag NOME_BANCO_DADOS

### Mais informações
A imagem utilizada para o banco de dados é a imagem oficial e sua documentação pode ser visualizada aqui: https://hub.docker.com/_/mysql/