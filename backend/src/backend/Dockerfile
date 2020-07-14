### [EN-US] Dockerfile using multi-stage builds to reduce file size ###
### [PT-BR] Dockerfile utilizando multi-stage builds para reduzir o tamanho do arquivo ###

#[EN-US] Downloading GoLang Alpine docker image
#[PT-BR] Baixando docker image do GoLang utilizando Alpine
FROM golang:1.14.4-alpine AS builder
#[EN-US] Installing necessary dependencies
#[PT-BR] Instalando dependências necessárias
RUN apk update && apk add git
RUN apk --no-cache add ca-certificates build-base
#[EN-US] Specifying directory and copying files
#[PT-BR] Especificando diretório e copiando os arquivos
WORKDIR /go/src/backend/app
COPY . .
#[EN-US] Fetching and installing microservice dependencies
#[PT-BR] Buscando e instalando dependências do microserviço
RUN go get -v -d ./...
RUN go build

FROM alpine:latest AS build
#[EN-US] Copying only necessary files from "origin" build
#[PT-BR] Copiando apenas arquivos necessários build "origin"
COPY --from=builder /go/src/backend/app/app .
CMD ["./app"]