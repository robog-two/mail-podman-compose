FROM docker.io/debian:latest

RUN apt update && apt upgrade -y && apt install -y postfix systemd

COPY etc-aliases /etc/aliases
COPY etc-mailname /etc/mailname
COPY main.cf /etc/postfix/main.cf
COPY master.cf /etc/postfix/master.cf

COPY ssl-cert-snakeoil.pem /etc/ssl/certs/ssl-cert-snakeoil.pem
COPY ssl-cert-snakeoil.key /etc/ssl/private/ssl-cert-snakeoil.key

CMD ["/usr/sbin/postfix", "start-fg"]
