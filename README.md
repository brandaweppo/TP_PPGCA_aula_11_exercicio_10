# Técnicas de Programação/PPGCA
## Exercício 10 - Aula 11

###### 1. Fazer um diretório local chamado *"solicitacoes-v4"*

###### 2. Acessar diretório correspondente
```
cd solicitacoes-v4/
```

###### 3. Criar diretórios da estrutura conforme os comandos abaixo:
```
mkdir app
```
e
```
mkdir atendente
```
e
```
mkdir nginx
```
e
```
mkdir scripts
```
e
```
mkdir web
```

###### 4. Fazer download dos arquivos *"docker-compose"* e *"docker-compose.override"* inserí-los dentro da raiz do diretório do projeto, chamado *"solicitacoes-v4"*:


###### 5. Listar diretórios existentes dentro de *solicitacoes-v4* e verificar se há "app", "atendente", "nginx", "scripts", "web" e "docker-compose" com o comando abaixo:
```
ls
```

###### 5. Fazer download dos arquivos *"app.sh"* e *"envia.py"* e inserí-los dentro do diretório chamado *"app"*.

###### 6. Fazer download dos arquivos *"atendente.sh"*, *"atendente.py"* e *"dockerfile"* inserí-los dentro do diretório chamado *"atendente"*.

###### 7. Fazer download do arquivo *"default.conf"* e inserí-lo dentro do diretório chamado *"nginx"*.

###### 8. Fazer download dos arquivos *"check.sql"* e *"init.sql"* e inserí-los dentro do diretório chamado *"scripts"*.

###### 9. Fazer download do arquivo *"index.html"* e inserí-lo dentro do diretório chamado *"web"*.

###### 10. Verificar se não há nada rodando do arquivo *"docker-compose"* com o comando abaixo:
```
docker-compose ps 
```
ou
```
docker-compose ps -a
```

###### 11. Se estiver algum componente ativo executar o comando abaixo para desativá-los:
```
docker-compose down
```

###### 12. Ativar arquivo docker-compose e deixá-lo em background e levantar 3 containers disponíveis para "atendente", utilizando o comando abaixo:
```
docker-compose up -d --scale atendente=3
```

###### 13. Executar o comando abaixo para verificar se os serviços estão ativos, identificados pelo status "up" conforme mostra a imagem logo a seguir:
```
docker-compose ps
```
![Captura de Tela (120)](https://user-images.githubusercontent.com/65691783/84554563-cffed600-acee-11ea-815c-1171bda28aeb.png)

###### 14. Acessar o navegador web e verificar se a aplicação está no *"localhost"*, conforme mostra a imagem abaixo:

![Captura de Tela (62)](https://user-images.githubusercontent.com/65691783/83930336-6f5f1e80-a76d-11ea-9a02-34be99d1ecc7.png)

###### 15. Verificar logs
```
docker-compose logs -t -f
```

###### 16. Verificar logs somente do atendente, executando o comando abaixo. Acompanhe um exemplo na imagem logo a seguir.
```
docker-compose logs -t -f atendente
```
![Captura de Tela (121)](https://user-images.githubusercontent.com/65691783/84553983-477f3600-acec-11ea-8dce-0a374693df68.png)

###### 17. Acessar localhost e realizar 3 testes de atendimento, após verifique se é possível visualizar as solicitações em "logs". Acompanhe um exemplo na imagem abaixo:

![Captura de Tela (122)](https://user-images.githubusercontent.com/65691783/84554436-2c152a80-acee-11ea-9336-63470c9c3197.png)

###### 18. Verificar se as informações estão sendo inseridas no banco de dados, executando o comando abaixo. Acompanhe um exemplo na imagem logo a seguir.
```
docker-compose exec db psql -U postgres -d solicitacoes -c 'select * from pedidos'
```
![Captura de Tela (123)](https://user-images.githubusercontent.com/65691783/84554512-8c0bd100-acee-11ea-83f4-5e84a80a93e4.png)
