# Dockerizando
==================================

Salve 0/.

Aqui vou passar algumas coisas que já utilizo com Docker como:

Graylog2
------------
O que é: *O Graylog é um sistema que tem como objetivo centralizar e catalogar log’s. Com o Graylog se torna mais simples a auditoria e a identificação de diversos eventos em uma rede corporativa.*

ADD: Vídeo Foda do Amigo Jefferson do Canal LinuxTips (https://www.youtube.com/watch?v=hg6m8ZPwh4k)

Nesse exemplo utilizamos o graylog2 All In One (https://hub.docker.com/r/graylog2/server/) para rodar o graylog2 já pré configurado.

OBS: Utilizando Docker tive a necessidade de centralizar os logs dos containers no graylog2, nesse exemplo já vamos configurar o container para enviar logs via GELF.. ;)

Git Documentação Graylog > https://github.com/Graylog2/documentation

![alt tag](https://github.com/gcalcettebr/dockerizando/blob/master/jpg/LogsInicio.png)

BORA > https://github.com/gcalcettebr/graylog2

Monitorando containers - cAdvisor / Prometheus / Grafana (Construção)
---------------------------------------------------------------------

Usando o basico do cAdvisor,Prometheus e grafana para monitoramento de containers.

Se liga nesses DashBoards.

![alt tag](https://github.com/gcalcettebr/dockerizando/blob/master/jpg/dashboardcontainers.png)
![alt tag](https://github.com/gcalcettebr/dockerizando/blob/master/jpg/hostdashboard.png)

Então Bora La > https://github.com/gcalcettebr/dockermonitor

Rodando Tomcat
--------------

Rodando Nginx+php
-----------------

=)

Requerimentos :
--------------
Ter o docker / docker-compose instalados.
(http://docs.graylog.org/en/2.1/pages/installation/os/debian.html)

Usando Ubuntu / Debian:
Instalando docker
-----------------
```shell
#curl -fsSL https://experimental.docker.com | sh
```
Instalando o Docker-compose
---------------------------
```shell
#wget https://github.com/docker/compose/releases/download/1.6.2/docker-compose-Linux-x86_64
#mv docker-compose-Linux-x86_64 /usr/local/bin/docker-compose
#chmod +x /usr/local/bin/docker-compose
```
Testando a parada:

```shell
#docker --version
Docker version 1.12.5, build 7392c3b, experimental
#docker-compose --version
docker-compose version 1.6.2, build 4d72027
```
BLZ Tudo Rodando!
