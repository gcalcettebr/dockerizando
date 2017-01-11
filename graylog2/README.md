Iniciando o Graylog2 no Docker
==================================

Executando o docker-compose
---------------------------

Bom vou explicar um pouco do arquivo .yml

O compose executa o mongo sem nenhuma configuralçao especial, executa o elasticsearch com as portas necessarias e executa o graylog2 com algumas configurações marotas.

As linhas padrões abaixo, é a configuração da TimeZone e  o envio de logs do container via GELF para o proprio Graylog2.
```shell
  environment:
    TZ: America/Sao_Paulo
  logging:
    driver: gelf
    options:
      gelf-address: "udp://127.0.0.1:12201"
```
Temos também essas linhas abaixo, as configurações de PASSWORD_SECRET e PASSWORD_SHA2 estão configuradas como user: admin pass: password123456 , O REST_TRANSPOR configurado como localhost , Os links para comunicação de todos os containers internamente e as portas de conexão necessarias. 
Para mais info de como trocar a PASS SECRET e Etcs: (http://docs.graylog.org/en/2.1/index.html)
```shell
    GRAYLOG_PASSWORD_SECRET: BmrrpND6CplVGbJ3e5InoZvLUbbGNJ7CykjMbeElArnEcslT82NFbhwP6dLxEkv0f2eKejLjTFdDP4OTCNGuwHt5Uj28FJ2O
    GRAYLOG_ROOT_PASSWORD_SHA2: a4dd5658ec0219465b705ea7c7435d9786a3c66d4f448cabd7488dabceafb699
    GRAYLOG_REST_TRANSPORT_URI: http://127.0.0.1:12900
  links:
    - some-mongo:mongo
    - some-elasticsearch:elasticsearch
  ports:
    - "9000:9000"
    - "12900:12900"
    - "12201:12201"
    - "12201/udp:12201/udp"
```

Falando agora de Persistência de Dados
--------------------------------------
Bom, como estamos rodando em container todo dado armazenado dentro do container sera perdido quando matarmos o container. 
Então configuramos os VOLUMES para um volume /data padrão , claro que voce pode fazer algo "melhor" mas aqui é apenas um exemplo. congifurando assim todos os arquivos de logs e configurações realizadas no graylog2 não seram perdidas.

Para saber mais sobre persistência de dados e tals 

[![Docker Hub](https://img.shields.io/badge/docker-swcc%2Fdocker--graylog2-blue.svg?style=flat)](https://hub.docker.com/r/graylog2/server/)

Executando o Graylog2
---------------------
```shell
$sudo git clone github.com/gcalcettebr/dockerizando.git
$cd graylog2
$sudo docker-compose up
```
Saida:
```shell
graylog_1            | 2017-01-11 19:10:54,859 INFO : org.graylog2.bootstrap.ServerBootstrap - Services started, startup times in ms: {InputSetupService [RUNNING]=29, OutputSetupService [RUNNING]=147, BufferSynchronizerService [RUNNING]=174, KafkaJournal [RUNNING]=189, JournalReader [RUNNING]=198, PeriodicalsService [RUNNING]=499, IndexerSetupService [RUNNING]=5083, JerseyService [RUNNING]=18039}
graylog_1            | 2017-01-11 19:10:54,882 INFO : org.graylog2.bootstrap.ServerBootstrap - Graylog server up and running.
```
Okay Graylog Rodando.

Acessando Pagina Web:
---------------------
http://127.0.0.1:9000/
![alt tag](https://github.com/gcalcettebr/dockerizando/blob/master/jpg/01-TelaLogin.png)

User: admin
Pass: password123456


