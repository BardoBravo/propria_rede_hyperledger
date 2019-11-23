# Primeira Fabric Network

## Pré-requisitos

### Instalação de GO - linguagem de programação

```
curl -O https://storage.googleapis.com/golang/go1.13.4.linux-amd64.tar.gz

tar -xvf go1.13.4.linux-amd64.tar.gz

sudo chown -R root:root ./go

sudo mv go /usr/local

export GOPATH=$HOME/go

export PATH=$PATH:/usr/local/go/bin:$GOPATH/bin
```

### Python 2.7

```
sudo apt-get install python

python --version
```

## Instalando Hyperledger v1.4
```
mkdir hl

cd hl

curl -sSL http://bit.ly/2ysbOFE | bash -s

export PATH=~/hl/fabric-samples/bin:$PATH
```

## Executando sua primeira network Hyperledger
Primeiro, vamos remover qualquer possível docker que esteja rodando localmente (incluido o Composer)
```
docker system prune -a

docker images purge

docker rmi $(docker images -a -q)

docker stop $(docker ps -a -q)

docker rm $(docker ps -a -q)

docker volume prune
```

Iniciando acesso à rede
```
cd hl/fabric-samples/first-network
```

Verifique o arquivo *byfn.sh*

Depois, execute o bash

```
./byfn.sh generate
```

Agora vamos executar nossa network
```
./byfn.sh up
```

Analisando os logs e os dockers, podemos ver a rede ativa
```
docker images

docker ps -a
```

