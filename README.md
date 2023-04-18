# desafio3-solucao

DESAFIO 3

O projeto info exibe informações sobre a data de build do projeto e possui uma página index.html.

O repositório de código fonte para build do projeto é: https://dev.azure.com/vibedesenvolvimento/Red Hat/_git/ex288-customize-s2i

O texto "Hello Class! DO288 rocks!!!" deve ser exibido no Browser ao clicar no link:

http://info-hello-class.apps.ocp.desenv.com/index.html 

O texto "Info: Page built on..." deve ser exibido no Browser ao clicar no link:

http://info-hello-class.apps.ocp.desenv.com/info.html 

COMO RESOLVER A QUESTÃO:

Projeto vem com um arquivo index.html.

criar o arquivo info.html.

Pode ser criado no arquibo assemble, ou manualmente mesmo.

Faça o clone do projeto no terminal. Ao entrar na pasta do repositório, faça:

ls -la

Os arquivo do source to image são ocutos e só aparecem com esse comando. eles ficam na pasta .s2i você deve customizar o arquivo assemble: .s2i/bin/assemble

Ao abrir o aarquivo assemble, veja o techo para copiar os arquivos html. Alterar o assemble para copiar todos os htmls. Salve o arquivo. comite o projeto. Inicie um build com oc start build. veja nos logs do build o progresso. Exponha a rota. Teste sua aplicação.


Para reproduzir a questão:

oc new-project info

*ATENÇÃO COM httpd:2.4~
* Você deve indicar o image stream adequado:
oc get is
o comando lista os image streams

oc new-app --name=hello-class httpd:2.4~https://github.com/leandroppereira/desafio3-solucao


Fique atento os logs do build:

oc logs -f buildconfig/hello-class

oc get svc

oc expose svc hello-class

Ele mostra o que você cuatomizou no arquivo assemble
