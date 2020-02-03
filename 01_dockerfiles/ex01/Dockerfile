FROM debian

RUN apt-get update && apt-get install wget -y bzip2 
# Adding a new user with its own directory in /opt/.
RUN useradd -d /opt/teamspeak3-server -m teamspeak3-user
# Downloading teamspeak server
RUN wget http://dl.4players.de/ts/releases/3.8.0/teamspeak3-server_linux_amd64-3.8.0.tar.bz2
# Then extract the files of the tarbal
RUN tar -jxvf teamspeak3-server_linux_amd64-3.8.0.tar.bz2
# Make folder for teamspeakServer
RUN mkdir /teamspeak3-server
# Move the files to the opt directory
RUN mv teamspeak3-server_linux_amd64/* /teamspeak3-server
# Change the permissions of the teamspeak server files
RUN chown teamspeak3-user:teamspeak3-user /teamspeak3-server -R
# Remove all the downloaded files
RUN rm -rf teamspeak3-server_linux_amd64-3.8.0.tar.bz2 teamspeak3-server_linux_amd64

# Accept Teamspeak Licence Agreement
ENV TS3SERVER_LICENSE=accept

# Expose ports: 9987=Voice 10011=ServerQuery 30033=FileTransfer
EXPOSE 10011 30033 9987/udp

ENTRYPOINT sh ./teamspeak3-server/ts3server_minimal_runscript.sh start

# docker build ./ -t ex01
# docker run -it --name teamspeakServer -p 9987:9987/udp -p 30033:30033 -p 10011:10011 --rm ex01