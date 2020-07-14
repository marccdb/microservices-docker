(FOR ENGLISH VERSION, PLEASE SCROLL FURTHER DOWN)

########################
## [PT-BR] Criação de solução para deploy em container de microserviços de backend e frontend. ##
*Atenção, você precisa ter instalado e configurado o Docker em sua máquina. Para mais informações, acesse docker.com/get-started

Ferramentas e procedimentos utilizados:
- Docker
- Docker Muli-stage builds
- Docker-Compose

#OVERVIEW DO DOCKER E DOCKER-COMPOSE#
O Docker-compose criará containers Docker e um ambiente virtual com para ambos os microserviços funcionarem e se relacionarem,
de forma automatizada, usando o arquivo docker-compose.yml como guia.
O processo utiliza as Dockerfiles como blueprints para criar as imagens Docker a partir de sistemas base Linux com as
dependências míninas adicionadas, para evitar que a imagem fique muito grande.
Dentro da pasta de cada microserviço, você encontrará os arquivos "Dockerfile" com as instruções de criação das imagens para cada serviço.

#INSTRUÇÕES#
- Abra seu terminal de preferência.
- Navegue até a pasta root do projeto. Você encontrará o arquivo "docker-compose.yml"
- No terminal, digite $docker-compose up
- As imagens serão automaticamente criadas, puxando as depêndências necessárias.
- Na primeira vez que digitar este comando, o processo será um pouco lento uma vez que
será feito o download das dependências porém nas próximas vezes, o Docker guardará os 
arquivos necessários em cache e o processo será muito mais rápido.
- Os containers serão automaticamente criados e você pode acessar o cliente através do endereço "localhost:8000".
- Sempre que houver alteração de código é necessário criar novas builds. Para isso, rode o comando $docker-compose up --build

Como recurso visual do processo, verificar o arquivo "Architecture.pdf".

Divirta-se =)

########################
## [EN-US] Creating a solution for frontend and backend microservices deployment ##
*Warning, you need to have installed and configured Docker before running these commands. For more information, please go to docker.com/get-started

Tools and procedures utilized:
- Docker
- Docker Muli-stage builds
- Docker-Compose

#DOCKER AND DOCKER-COMPOSE OVERVIEW#
Docker-Compose will create Docker containers and a virtual ambient for the microservices to interact with each other in an automatized way, using the docker-compose.yml file as a guide.
The whole process uses Dockerfiles and blueprints to generate docker images based on Linux systems using just the needed dependencies, keeping the final image within an acceptable size.
Inside each microservice folder, you'll find "Dockerfile" files with instructions for building each image separately.

##INSTRUCTIONS##
- Open your preferred terminal
- Navigate to the project root folder. You'll find a "docker-compose.yml" file.
- On your terminal, type $docker-compose up
- The images will be automatically created and all dependencies will be downloads.
- The first time you execute this command, it will take some time to download all the dependencies. After that, the process will be much quicker!
- The Docker containers will be automatically created and you can access the client through the address "localhost:8000".
- Whenever there are code changes, a new build is necessary. For that, run the command $docker-compose up --build

As a visual resource of the whole process, please check the "Architecture.pdf" file.

Have fun! =)