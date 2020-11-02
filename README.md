# Criando um ambiente de Desenvolvimento com Docker

### Exemplificando como criar um ambiente de desenvolvimento com DOCKER utilizando rede pessonalizada para comunicação entre os containers. 

docker network create --driver bridge DEV-Network

### Para visualizar todas as redes dentro do Docker

docker network ls

### Incluindo um conteiner a uma rede

docker run -it --name My-Ubuntu --network DEV-Network ubuntu 

Interativo para fazer alguns teste, como por exemplo ping, mas pode ser criado sem o uso de -it

Observação: Ao criar cada container referente ao serviços que deseja, e que os mesmos façam parte da rede DEV-Network ao cria inclua --network e o nome da rede. 

### Uma forma de verificar que o conteiner está na rede definida, execute o comando abaixo:

docker inspect My-Ubuntu 

Observe na sessão "Networks": o nome da rede DEV-Network e o "IPAddress": obtido. 

Com esse IPAddress é possivel fazer um teste de ping entrando nos container.

ou 

Dentro do container executar o comando hostname -i dentro do interativo, assim será mostrado o IP.

