#  Gerenciando Instâncias EC2 na AWS

##  Introdução
Nesta etapa do bootcamp, criei uma arquitetura simples usando **Amazon EC2**, **Amazon S3** e **AWS Lambda** para simular um sistema de upload e processamento de músicas.  
O objetivo foi aplicar os conceitos aprendidos sobre instâncias EC2, armazenamento e funções serverless, consolidando o aprendizado de forma prática.



## Descrição do Desafio
Este laboratório tem como objetivo consolidar os conhecimentos em **gerenciamento de instâncias EC2** na AWS.  
O entregável consiste em um repositório organizado contendo anotações, diagramas e insights obtidos durante a prática.



## Objetivos de Aprendizagem
Ao finalizar este desafio, fui capaz de:
- Criar e gerenciar uma instância **EC2**.
- Configurar **armazenamento S3** para upload e consumo de arquivos.
- Criar uma função **AWS Lambda** acionada por eventos S3.
- Documentar a experiência de forma clara para uso futuro.



##  Arquitetura Criada
A arquitetura desenvolvida segue o diagrama abaixo:

<img src=".img/diagrama arquitetura.jpeg" alt="instancia EC2" width="450"/>

###  Explicação da Arquitetura
1. **Usuário** faz upload de música através de uma aplicação hospedada em uma instância **EC2**.
2. O arquivo é salvo no **Amazon S3**.
3. O **S3** dispara um **evento de trigger** que ativa uma função **Lambda**.
4. A função Lambda processa a música (ex: conversão de formato, normalização de áudio).
5. O resultado é salvo de volta no **S3** e disponibilizado para o usuário consumir.



##  Conceitos Importantes

### 🔹 Amazon EC2
O **Amazon EC2** (Elastic Compute Cloud) permite criar servidores virtuais sob demanda, escaláveis e configuráveis de acordo com a necessidade do projeto.  
É a base para rodar aplicações de forma segura e altamente disponível.



### 🔹 Snapshots EBS
- **EBS Snapshots** são backups incrementais dos volumes EBS (Elastic Block Store).
- Eles permitem restaurar o estado de um volume em um ponto específico no tempo.
- Muito útil para garantir **resiliência**, criar **backups regulares** e **replicar dados** em outras regiões.



### 🔹 Amazon AMI
- **AMI (Amazon Machine Image)** é uma imagem que contém o sistema operacional, pacotes e configurações necessárias para iniciar uma instância EC2.
- Pode ser usada para padronizar o ambiente de diversas instâncias.
- Exemplo: criar uma AMI de um servidor já configurado e usar como base para iniciar novas instâncias.


