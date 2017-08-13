FROM	debian

RUN	apt-get update -y && \
	apt-get install apt-utils -y && \
	apt-get install curl -y && \
	apt-get install bzip2 -y && \
	useradd teamspeak

WORKDIR	/home/t3

RUN	curl http://dl.4players.de/ts/releases/3.0.13.6/teamspeak3-server_linux_amd64-3.0.13.6.tar.bz2 > teamspeak-server.tar.bz2 && \
	tar -xjvf teamspeak-server.tar.bz2

WORKDIR	teamspeak3-server_linux_amd64
USER	teamspeak

EXPOSE	9987/UDP
EXPOSE	30033
EXPOSE	10011

ENTRYPOINT ["sh", "ts3server_minimal_runscript.sh"]
