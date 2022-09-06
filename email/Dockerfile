FROM ubuntu:20.04

# Atualizando repositorio e realizando o upgrade dos pacotes
RUN apt update \
     && apt upgrade -y 

#Instalação do postfix e dovecote, além de alguns utilitários
RUN apt install postfix dovecot-core dovecot-imapd vim dnsutils iputils-ping -y

#Copiando os arquivos configurados para as aplicações subirem
COPY postfix/main.cf /etc/postfix/main.cf
COPY dovecot/dovecot.conf /etc/dovecot/dovecot.conf
COPY dovecot/10-auth.conf /etc/dovecot/conf.d/10-auth.conf
COPY dovecot/10-mail.conf /etc/dovecot/conf.d/10-mail.conf
COPY dovecot/10-master.conf /etc/dovecot/conf.d/10-master.conf

