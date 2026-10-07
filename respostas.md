# Respostas · Avaliação Prática de Docker · ViaSerra Transportes (Turma C)

Nome: Felipe Novais
Matrícula: 26174866
Usuário do GitHub: https://github.com/felipenovais-tech
Usuário do Docker Hub: felipenovais00

Responda com as suas palavras e com o que aconteceu na SUA máquina. Resposta curta e certa vale mais
do que texto longo copiado. Resposta que contradiz o seu próprio Dockerfile vale zero.

## Parte 1 · Dockerfile do portal

1. Qual imagem base você usou e qual o tamanho final da imagem do portal (saída de `docker images`)?

nginx:1.25-alpine e o da imagem ficou 74.1MB (com 20.5MB de Content Size).

2. Em qual pasta do container o Nginx procura os arquivos do site? Mostre o comando que você usou para
   conferir que o `index.html` está lá dentro.

   Fica nessa pasta /usr/share/nginx/html/ e o comando é docker exec teste-portal ls /usr/share/nginx/html/

## Parte 2 · Docker Hub

3. Nome completo da imagem publicada e link público do repositório no Docker Hub.

Nome da imagem: felipenovais00/viaserra-portal:1.0-26174866
Link: https://hub.docker.com/repository/docker/felipenovais00/viaserra-portal/general

4. Se você mudar o HTML, quais comandos precisa rodar para que a versão nova chegue ao Docker Hub?

## Parte 3 · Página de manutenção

5. Preencha uma linha por defeito encontrado. Defeito inexistente listado aqui desconta pontos.

#	Instrução	O que estava errado	O que você viu acontecer	Como corrigiu

1	WORKDIR /usr/share/nginx	Mudou a pasta de trabalho padrão do Nginx, travando o processo principal.	O container desligava sozinho logo após subir (Status: Exited).	Removi a linha ou mudei para WORKDIR /.
2	(Faltava instrução)	Não havia comando COPY para incluir a pasta ./site/ na imagem.	Exibia a página padrão "Welcome to Nginx" em vez da página do fornecedor.	Adicionei a instrução COPY ./site/ /usr/share/nginx/html/.
3	(Faltava instrução)	Não possuía a porta 80 devidamente documentada no arquivo.	Dificuldade ou avisos no mapeamento e documentação da porta do container.	Adicionei a instrução EXPOSE 80 no final do arquivo.

6. Qual a diferença entre `-p 7042:80` e `-p 80:7042` no `docker run`? Qual dos dois números é a porta do container?

## Parte 4 · Primeiro docker-compose

7. Escreva os dois comandos `docker run` que fariam o mesmo que o seu `docker-compose.yml`.

8. Qual comando derruba os dois containers de uma vez?

## Verificador

9. Código de conclusão impresso pelo verificador:

```
(cole aqui)
```
