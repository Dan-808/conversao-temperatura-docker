FROM ubuntu
RUN apt update &&\
    apt install curl --yes &&\
    curl -fsSL https://deb.nodesource.com/setup_22.x | bash - &&\
    apt update &&\
    apt-get install -y nodejs
# juntei tres tres comando em um RUN só porue eles dependem do apr update
WORKDIR /app
COPY . .
RUN npm install
ENTRYPOINT [ "node", "server.js" ]
# nesse caso utilizei entrypoint para rodar o comando "node server.js" ao inves de RUN porque se eu colocasse o RUN ele iria startar o app na construção da imagem e eu quero que de start na finalização da criaçao do container, por isso nessa caso é melhor usar o entrypoint.