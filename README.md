# Dockerizando

Salve 0/.

Aqui vou passar algumas coisas que ja utilizo com docker como:

### Graylog2
Oque é: *O Graylog é um sistema que tem como objetivo centralizar e catalogar log’s. Com o Graylog se torna mais simples a auditoria e a identificação de diversos eventos em uma rede corporativa.*

ADD: Video Foda do Amigo Jefferson do Canal LinuxTips (https://www.youtube.com/watch?v=hg6m8ZPwh4k)

Nesse exemplo utilizamos o graylog2 All In One (https://hub.docker.com/r/graylog2/server/) para rodar o graylog2 já pré configurado.

OBS: Utilizando Docker tive a necessidade de centralizar os logs dos containers no graylog2, nesse exemplo ja vamos configurar o container para enviar logs via GELF.. ;)

Git Documentação Graylog > https://github.com/Graylog2/documentation

![alt tag](https://github.com/gcalcettebr/dockerizando/blob/master/jpg/LogsInicio.png)

BORA > https://github.com/gcalcettebr/dockerizando/tree/master/graylog2

#### Monitoramento - cadvisor / Prometheus / Grafana (Construção)

=)
