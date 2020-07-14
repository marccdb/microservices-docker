## [PT-BR] Arquivo de criação das imagens Docker (Não foi usado multi-stage pois a imagem final não teve grande diferença de tamanho).
## [EN-US] Image creations file (Multi-stage was not used because there was not a big difference in image size).

## [PT-BR] Utilizando Debian como imagem padrão por ter mais estabilidade e performance com ambiente Python.
## [EN-US] Using Debian as a base image mostly because of stability and performance within Python enviroment.
FROM debian:buster-slim

WORKDIR /src/frontend/app
COPY . .
## [PT-BR] Instalando dependências necessárias
## [EN-US] Installing necessary dependencies
RUN apt update && apt install --no-install-recommends python3 python3-pip --yes && pip3 install -U pip && pip3 install -r requirements.txt &&\
apt purge -y python3-pip && apt autoremove -y && apt clean -y
## [PT-BR] Inicializando o programa
## [EN-US] Initializing the program
CMD sh -c 'python3 frontend.py'