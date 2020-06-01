# Teste para Analista de Infraestrutura

* Para concluir o teste você deve utilizar ambiente grátis da AWS.

Etapa 1 - Configurar um bucket de arquivos.
    Deve subir a imagem "arquivos/imagem.png" e disponibilizar através de um link público

Etapa 2 - Configurar um servidor WEB para servir a aplicação "arquivos/index.html"
    - O Sistema Operacional deve ser CentOS.
    - Deve criar o usuário imts com a senha 2I0M2T0S@so e permissão de root no sistema operacional.
    - O Servidor WEB deve ser o httpd.
    - Deve ser configurado um certificado SSL Let's Encrypt.
    - Deve configurar uma regra na AWS para liberar o acesso a porta 22, 80 e 443 apenas para o IP 189.84.119.2.
    - Deve colocar o link da imagem disponibilizado na etapa 1 dentro do arquivo "arquivos/index.html" 
    linha 11 <img src="COLOCAR_AQUI_O_LINK_DA_IMAGEM">

Etapa 3 - Configurar um servidor de banco de dados.
    - O Sistema Operacional deve ser Debian.
    - Deve criar o usuário imts com a senha 2I0M2T0S@so e permissão de root no sistema operacional.
    - O SGBD deve ser o PostgreSQL 12.
    - Deve criar o usuário imts com a senha 2I0M2T0S no banco de dados.
    - Deve criar um banco chamado cidades_estados.
    - Deve subir usar o arquivo "arquivos/script.sql" para criar a estrutura e dados no banco criado anteriormente.
    - O Acesso ao banco de dados deve ser postgresql.teste.com.br na porta 2345.
    - Deve configurar uma regra na AWS para liberar o acesso a porta 22 e 2345 apenas para o IP 189.84.119.2.

Etapa 4 - Configurar um servidor DNS.
    - O Sistema Operacional deve ser CentOS.
    - Deve criar o usuário imts com a senha 2I0M2T0S@so e permissão de root no sistema operacional.
    - Configurar uma zona teste.com.br.
    - Configurar um registro do tipo A apontando o dns.teste.com.br para o IP público do servidor DNS.
    - Configurar um registro do tipo A apontando o aplicacao.teste.com.br para o IP público do servidor WEB configurado na etapa 2.
    - Configurar um registro do tipo A apontando o postgresql.teste.com.br para o IP público do servidor de banco de dados configurado na etapa 3.
    - Configurar um registro do tipo CNAME apontando o a.teste.com.br para aplicacao.teste.com.br.
    - Configurar um registro do tipo CNAME apontando o p.teste.com.br para postgresql.teste.com.br.



# Ao final do teste iremos configurar um computador usando o DNS configurado no passo 4 e deverá atender aos seguintes requisitos.

1 - Acessar a aplicação através da URL https://aplicacao.teste.com.br.
2 - Acessar via SSH o servidor WEB através dos seguintes dados de acesso:
    Host: a.teste.com.br
    User: imts
    Pass: 2I0M2T0S@so
3 - Acessar o banco de dados através dos seguintes dados de acesso:
    Host: postgresql.teste.com.br
    Port: 2345
    User: imts
    Pass: 2I0M2T0S
4 - Acessar via SSH o servidor de banco de dados através dos seguintes dados de acesso:
    Host: p.teste.com.br
    User: imts
    Pass: 2I0M2T0S@so
5 - Acessar via SSH o servidor DNS através dos seguintes dados de acesso:
    Host: dns.teste.com.br
    User: imts
    Pass: 2I0M2T0S@so