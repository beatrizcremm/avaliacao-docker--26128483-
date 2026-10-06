# Respostas · Avaliação Prática de Docker · Cooperativa AgroVale (Turma A)

Nome:BEATRIZ ALBUQUERQUE CREMM
Matrícula:26128483
Usuário do GitHub:beatrizcremm
Usuário do Docker Hub:beatrizcremm13

Responda com as suas palavras e com o que aconteceu na SUA máquina. Resposta curta e certa vale mais
do que texto longo copiado. Resposta que contradiz o seu próprio Dockerfile ou compose vale zero.

## Parte 1 · Dockerfile do portal

1. Qual imagem base você usou e qual o tamanho final da imagem do portal (saída de `docker images`)?
R: Usei a imagem base nginx:1.27-alpine. O tamanho final da imagem foi 73.6 MB, conforme o comando docker images.

2. Em qual pasta do container o Nginx procura os arquivos do site? Mostre o comando que você usou para
   conferir que o `index.html` está lá dentro.
R: O Nginx procura os arquivos em /usr/share/nginx/html. Conferi com o comando docker exec manut ls -la /usr/share/nginx/html.

## Parte 2 · Docker Hub

3. Nome completo da imagem publicada e link público do repositório no Docker Hub.
R: A imagem publicada é biacremm13/agrovale-portal:1.0-26128483. O repositório público no Docker Hub é:
https://hub.docker.com/r/biacremm13/agrovale-portal

4. Por que o `docker login` foi feito com um token de acesso e não com a senha da conta?
R: Porque o token é mais seguro para autenticação no Docker Hub, pode ter permissões controladas e pode ser revogado sem precisar alterar a senha da conta.

## Parte 3 · Página de manutenção

5. Preencha uma linha por defeito encontrado. Defeito inexistente listado aqui desconta pontos.

| # | Instrução | O que estava errado | O que você viu acontecer | Como corrigiu |
|---|---|---|---|---|
| 1 | | | | |
| 2 | | | | |
| 3 | | | | |

6. Qual a diferença entre `-p 7042:80` e `-p 80:7042` no `docker run`? Qual dos dois números é a porta do container?
R: No comando -p 7042:80, a porta 7042 é a porta do computador (host) e a porta 80 é a porta do container. Já -p 80:7042 faz o contrário. A porta do container é sempre o segundo número.
## Parte 4 · docker-compose.yml

7. No serviço `blog`, por que `WORDPRESS_DB_HOST` recebe `db` e não `localhost`?
R: Porque no Docker Compose o serviço do banco se chama db. Dentro do container do WordPress, localhost seria o próprio container do WordPress, e não o banco MariaDB.

8. Por que o serviço `db` não publica a porta 3306? Se precisar consultar o banco, como faz sem publicar
   a porta? Mostre o comando.
R: O serviço db não publica a porta 3306 porque o WordPress acessa o banco pela rede interna do Docker Compose. Para consultar o banco sem publicar a porta, posso usar: docker compose exec db mariadb -u agrovale -p agrovale_blog

## Parte 5 · Persistência

9. Quais comandos você usou para derrubar e subir a stack? Qual comando teria apagado o post que você criou,
   e por quê?
R: Usei os comandos docker compose down e depois docker compose up -d para derrubar e subir a stack. O comando que apagaria o post seria docker compose down -v, porque o -v remove os volumes nomeados onde os dados do WordPress e do banco ficam armazenados.

10. Código de conclusão impresso pelo verificador:

```
(cole aqui)
```
