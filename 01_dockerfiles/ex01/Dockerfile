# Image de travail
FROM debian

#  9987 port pour la voix
# 10011 port pour le query du serveur
# 30033 port pour le transfere de fichier
EXPOSE 9987/udp
EXPOSE 10011
EXPOSE 30033

# Accepter la liscence de ts
ENV TS3SERVER_LICENSE accept

# installer le serveur ts
RUN apt-get update -y
RUN apt-get install wget bzip2 -y
RUN wget 'http://dl.4players.de/ts/releases/3.5.0/teamspeak3-server_linux_amd64-3.5.0.tar.bz2'
RUN tar -xvjf teamspeak3-server_linux_amd64-3.5.0.tar.bz2
RUN rm -rf teamspeak3-server_linux_amd64-3.5.0.tar.bz2

# aller dans le dossier de conf du serveur ts
WORKDIR /teamspeak3-server_linux_amd64

ENTRYPOINT ["sh", "ts3server_minimal_runscript.sh"]
