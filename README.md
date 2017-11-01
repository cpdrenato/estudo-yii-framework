# estudo-yii-framework

A instalação do Yii envolve principalmente, as duas etapas seguintes:

Fazer o Download do Yii Framework em:
# yiiframework.com.
Descompactar o arquivo do Yii em um diretório acessível a Web.


### Dica: O Yii não precisa ser instalado em um diretório acessível a Web. Uma aplicação Yii tem uma entrada de script que normalmente é o único arquivo que precisa ser exposto para os usuários da Web. Outros scripts de PHP, incluindo os do Yii, devem ter o acesso protegido, uma vez que podem ser explorados por hackers.

1. Requisitos 
Depois de instalar o Yii, você pode verificar se o servidor satisfaz todos os requisitos de de utilização do Yii. Você pode fazê-lo, acessando o script verificador de requisitos na seguinte URL em um navegador Web:

http://nomedoservidor/caminho/do/yii/requirements/index.php
O requisito mínimo para o Yii é que seu servidor Web tenha suporte ao PHP 5.1.0 ou acima. O Yii foi testado com Apache HTTP Server nos sistemas operacionais Windows e Linux. Também pode ser executado em outros servidores Web e plataformas desde que tenha o PHP 5.

# Outro link: http://www.yiiframework.com/doc/guide/1.1/pt/quickstart.first-app

# Yii2 Framework Instalação – Composer


1 php -v

1) Instalar o Composer

Via terminal, navegue até a pasta onde deseja criar o projeto (no meu caso D:/xampp/htdocs/yii2advanced) e rode o seguinte comando:

php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php -r "if (hash_file('SHA384', 'composer-setup.php') === '669656bab3166a7aff8a7506b8cb2d1c292f042046c5a994c43155c0be6190fa0355160742ab2e1c88d40d5be660b410') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
php composer-setup.php
php -r "unlink('composer-setup.php');"

Esse comando já irá buscar e instalar a versão mais recente do Composer (será criado o arquivo composer.phar na raiz do projeto). Para mais consultas e informações sobre visite a página oficial:
https://getcomposer.org

2) Instalar Composer Asset Plugin para o Yii2

Em sequência, rode o seguinte comando para instalar o Asset Plugin, dependências necessárias para o pleno funcionamento do Yii2 Framework:

Yii2 Composer Asset

1
php composer.phar global require "fxp/composer-asset-plugin:^1.2.0"


3) Instalar o Yii2 Framework

Finalmente instalamos o Yii2 Framework já buscando e instalando as suas dependências atualizadas graças ao Composer. No mesmo local, rode o seguinte comando no terminal e aguarde a instalação terminar, pode demorar um pouco dependendo da velocidade da internet.

 

1
php composer.phar create-project yiisoft/yii2-app-advanced advanced 2.0.11

3) Init e Migration inicial

A instalação via Composer criou uma nova pasta com todas as dependências necessárias. Uma nova instalação requer uma pasta vazia, por esse motivo a instalação não foi feita na raiz do projeto. Você pode mover o arquivo composer.phar para a nova pasta ou mover os arquivos da pasta para onde desejar.

Agora devemos iniciar o Yii2 com o comando INIT, e definir se vamos roda-lo em modo produção ou desenvolvimento, no meu caso em desenvolvimento. Para fazer o init, na raiz do seu projeto Yii digite o seguinte comando:

 

1
php init

Após selecionar o modo (Development no caso) e confirmar digitando YES o Yii2 irá criar os arquivos necessários (como o index.php na pasta web e o main-local.php que será utilizado a seguir) e dar permissões as pastas que ele utilizará para criação de arquivos, como por exemplo a pasta assets.

 

Para finalizar, vamos editar o arquivo main-local.php, localizado na pasta: commom/config. Esse arquivo irá conter as configurações locais e nele iremos definir nossa conexão com o banco de dados.

Como estamos rodando em localhost é ele que iremos editar, caso seu projeto estiver em um servidor em produção edite as mesmas configurações no arquivo main.php.

Após configurar a conexão com o banco de dados vamos fazer nosso migrate inicial para o Yii2 criar as tabelas user e migration. Sendo a user onde são gravados os usuários e a migration onde o Yii2 controla as migrations criadas.

Para fazer o migration digite o seguinte comando e confirme digitando: yes

 

1
php yii migrate

Pronto! O seu Yii2 Framework esta instalado, atualizado e configurado com o seu banco de dados. Você pode testar acessando diretamente a pasta frontend/web ou backend/web ou rodando um servidor local como o PHP Built In. Para rodar o PHP Built In basta via terminar navegar até a pasta que deseja, por exemplo a frontend/web e digitar o comando:

 

1
php -S localhost:8000
 

Após isso acessar o projeto digitando o endereço informado: localhost:8000

Se desejar utilize a mesma lógica para o backend da aplicação. Para testar o Yii2, navegue até a área signup do frontend e faça seu cadastro. Verá que o Yii2 já irá criar seu usuário na tabela user e realizar o login que deixará você ter acesso a área de backend da aplicação. A instalação padrão do Yii2 já possuí um cadastro e controle de acessos básicos como padrão.

