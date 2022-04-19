# materialdeapoio
Lista de conteúdo geral para ajudar no desenvolvimento de alguns projetos

Um modelo para fazer um bom README.md
https://gist.github.com/lohhans/f8da0b147550df3f96914d3797e9fb89?fbclid=IwAR3AdQoT-u7chHpDkGmaOp4JFw5YbY4UiCtCtNHwE4qGaSzL_hsfTzVIcyQ


**** Recursos Always Free
https://docs.oracle.com/pt-br/iaas/Content/FreeTier/freetier_topic-Always_Free_Resources.htm

Compute
Todas as tenancies têm um conjunto de recursos Always Free no serviço Compute para criar instâncias de máquina virtual (VM) de computação. Você deve criar as instâncias de computação Always Free em sua região home.


O Fluxograma na Vida de um Programador // Vlog #27
https://www.youtube.com/watch?v=i74ueEU6zIE


drawio



Elaboração de Fluxogramas de Processos
https://www.youtube.com/watch?v=k7AgUN0SYDk



Criando contribuição open-source no Github do zero! | Diego Fernandes

https://www.youtube.com/watch?v=mcd7lqpUzIA

Armazenamento na nuvem
https://www.youtube.com/watch?v=S9hDjLw7G8I


Google Cloud: Controlando Custos de Rede
https://www.youtube.com/watch?v=xH86IsUOjiY



Brasileiro vira notícia com suas habilidades em CSS e Design
https://www.youtube.com/watch?v=xx01-s_Q-mU

Isometric Cards - Pure CSS3
https://www.youtube.com/watch?v=YqHSUueLucY



Como perder um patrocínio em 2 minutos! Sikêra Jr ao vivo.
https://www.youtube.com/watch?v=LLz38nbmw-Y



Porque Eu Virei Um Problema Para os Meus Projetos Open Source

https://www.youtube.com/watch?v=amdnXhAaA1M

https://github.com/BrasilAPI/cep-promise


Ambientes Back-End com Docker + VS Code // Mão no Código #3
https://www.youtube.com/watch?v=97jWpWp4Pnc


index.php
=================================================================
<?php phpinfo(); ?>



docker-compose.yml
=================================================================
php:
  build: .
  ports:
   - "80:80"
   - "443:443"
   volumes:
    - ./www:/var/www/html
   links:
    - db 

db:
  image: mysql:5.7
  volumes:
    - /var/lib/mysql
  environment:
    - MYSQL_ROOT_PASSWORD=myrootpass
    - MYSQL_DATABASE=mydb


Dockerfile
=================================================================
FROM php:7.2-apache
RUN docker-php-ext-install mysqli
RUN a2enmod rewrite







=========================================================================
Docker + VS Code #CDFTV #MaoNoCodigo3
docker-compose-wordpress.yml
version: '3.3'

services:
   wordpress_db:
     image: mysql:5.7
     volumes:
       - db_data:/var/lib/mysql
     restart: always
     environment:
       MYSQL_ROOT_PASSWORD: myrootpass
       MYSQL_DATABASE: wordpress
       MYSQL_USER: wordpress
       MYSQL_PASSWORD: wordpress

   wordpress:
     depends_on:
       - wordpress_db
     image: wordpress:latest
     ports:
       - "80:80"
       - "443:443"
     restart: always
     environment:
       WORDPRESS_DB_HOST: wordpress_db:3306
       WORDPRESS_DB_USER: wordpress
       WORDPRESS_DB_PASSWORD: wordpress

   phpmyadmin:
    depends_on:
      - wordpress_db
    image: phpmyadmin/phpmyadmin
    restart: always
    ports:
      - 88:80
    environment:
      PMA_HOST: wordpress_db:3306
      MYSQL_ROOT_PASSWORD: myrootpass

volumes:
    db_data:
    
    
    
    
    
    
    ===================================================================================================
    
    docker-compose.yml
php:
  build: .
  ports:
   - "80:80"
   - "443:443"
  volumes:
   - ./www/:/var/www/html
  links:
   - db

db:
  image: mysql:5.7
  volumes:
   - /var/lib/mysql
  environment:
   - MYSQL_ROOT_PASSWORD=myrootpass
   - MYSQL_DATABASE=mydatabase
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    






===================================================================================================

Dockerfile
FROM php:7.2-apache
RUN docker-php-ext-install mysqli
RUN a2enmod rewrite
























===================================================================================================
Olá Gabriel! Primeiramente, agradeço a vocês pelo vídeo, foi uma ótima dica demostrar a integração do VSCode com o Docker. Parabéns!

Eu estive testando o docker, o segundo docker-compose (docker-compose.yml) e vi que está faltando a linha service. Por isso, para funcionar no meu ambiente de teste, tive que adicionar as linhas version e service no início do arquivo.

version: '3.3'

services:
  php:
    build: .
    ports:
    - "80:80"
    - "443:443"
    volumes:
    - ./www/:/var/www/html
    links:
    - db

  db:
    image: mysql:5.7
    volumes:
    - /var/lib/mysql
    environment:
    - MYSQL_ROOT_PASSWORD=myrootpass
    - MYSQL_DATABASE=mydatabase








































===================================================================================================
