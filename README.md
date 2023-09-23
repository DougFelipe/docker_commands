# Lista de comandos Uteis do Docker

## 1. Comandos Básicos

### 1. Faz o pull de uma imagem do Docker Hub (versão mais recente)
docker pull nome_da_imagem

### 2. Faz o pull de uma imagem com uma tag específica
docker pull nome_da_imagem:tag

### 3. Exibe uma lista de imagens locais
docker images

### 4. Exibe uma lista de imagens locais em um formato mais detalhado
docker images -a

### 5. Remove uma ou mais imagens locais (use -f para forçar)
docker rmi nome_da_imagem

### 6. Remove todas as imagens não usadas
docker image prune

### 7. Remove todas as imagens locais (cuidado ao usar)
docker rmi $(docker images -a -q)

### 8. Salva uma imagem em um arquivo .tar
docker save -o nome_da_imagem.tar nome_da_imagem

### 9. Carrega uma imagem a partir de um arquivo .tar
docker load -i nome_da_imagem.tar

### 10. Cria uma imagem a partir de um contêiner em execução
docker commit meu_contêiner nome_da_imagem:tag

### 11. Cria uma imagem a partir de um Dockerfile no diretório atual
docker build -t nome_da_imagem:tag .

### 12. Renomeia uma imagem local
docker tag nome_atual_da_imagem novo_nome_da_imagem

### 13. Envia uma imagem para um registro Docker (como o Docker Hub)
docker push nome_da_imagem

### 14. Exibe o histórico de uma imagem, incluindo camadas e metadados
docker history nome_da_imagem

### 15. Inspect uma imagem para obter detalhes específicos
docker image inspect nome_da_imagem

### 16. Exibe estatísticas de uso de espaço em disco das imagens
docker system df

### 17. Prune imagens não usadas, incluindo as não marcadas como "dangling"
docker image prune -a

### 18. Atualiza todas as imagens locais para suas versões mais recentes
docker images | awk '{print $1}' | xargs -L1 docker pull

### 19. Exibe informações sobre uma imagem, incluindo metadados
docker image inspect nome_da_imagem

### 20. Analisa e verifica se há atualizações de segurança em imagens
docker scan nome_da_imagem

## 2. Gerenciando Imagens

### 1. Faz o pull de uma imagem do Docker Hub (versão mais recente)
docker pull nome_da_imagem

### 2. Faz o pull de uma imagem com uma tag específica
docker pull nome_da_imagem:tag

### 3. Exibe uma lista de imagens locais
docker images

### 4. Exibe uma lista de imagens locais em um formato mais detalhado
docker images -a

### 5. Remove uma ou mais imagens locais (use -f para forçar)
docker rmi nome_da_imagem

### 6. Remove todas as imagens não usadas
docker image prune

### 7. Remove todas as imagens locais (cuidado ao usar)
docker rmi $(docker images -a -q)

### 8. Salva uma imagem em um arquivo .tar
docker save -o nome_da_imagem.tar nome_da_imagem

### 9. Carrega uma imagem a partir de um arquivo .tar
docker load -i nome_da_imagem.tar

### 10. Cria uma imagem a partir de um contêiner em execução
docker commit meu_contêiner nome_da_imagem:tag

### 11. Cria uma imagem a partir de um Dockerfile no diretório atual
docker build -t nome_da_imagem:tag .

### 12. Renomeia uma imagem local
docker tag nome_atual_da_imagem novo_nome_da_imagem

### 13. Envia uma imagem para um registro Docker (como o Docker Hub)
docker push nome_da_imagem

### 14. Exibe o histórico de uma imagem, incluindo camadas e metadados
docker history nome_da_imagem

### 15. Inspect uma imagem para obter detalhes específicos
docker image inspect nome_da_imagem

### 16. Exibe estatísticas de uso de espaço em disco das imagens
docker system df

### 17. Prune imagens não usadas, incluindo as não marcadas como "dangling"
docker image prune -a

### 18. Atualiza todas as imagens locais para suas versões mais recentes
docker images | awk '{print $1}' | xargs -L1 docker pull

### 19. Exibe informações sobre uma imagem, incluindo metadados
docker image inspect nome_da_imagem

### 20. Analisa e verifica se há atualizações de segurança em imagens
docker scan nome_da_imagem

### 21. Cria uma imagem com base em um Dockerfile em um diretório específico
docker build -t nome_da_imagem:tag /caminho/do/Dockerfile

### 22. Remove todas as imagens não usadas e contêineres parados
docker system prune -a

### 23. Copia arquivos ou diretórios do sistema local para um contêiner
docker cp arquivo/diretório meu_contêiner:/caminho/no/contêiner

### 24. Copia arquivos ou diretórios de um contêiner para o sistema local
docker cp meu_contêiner:/caminho/no/contêiner arquivo/diretório

### 25. Lista as camadas de uma imagem
docker history nome_da_imagem

### 26. Gera um Dockerfile a partir de um contêiner em execução
docker container commit meu_contêiner nome_da_imagem:tag

### 27. Analisa e verifica se há vulnerabilidades de segurança em uma imagem
docker scan nome_da_imagem

### 28. Inspect uma imagem para obter informações detalhadas em formato JSON
docker image inspect --format '{{json .Config.ExposedPorts}}' nome_da_imagem

### 29. Exibe as camadas de sistema de arquivos de uma imagem
docker image history nome_da_imagem

### 30. Exibe o tamanho de uma imagem em formato legível pelo usuário
docker image inspect --format='{{.Size}}' nome_da_imagem

### 31. Filtra imagens por rótulo
docker images -f "label=meu_rótulo"

### 32. Exibe informações resumidas sobre uma imagem
docker image ls --format "table {{.Repository}}\t{{.Tag}}\t{{.Size}}"

### 33. Exibe a data e a hora em que uma imagem foi criada
docker inspect --format='{{.Created}}' nome_da_imagem

### 34. Exibe metadados específicos de uma imagem
docker image inspect --format='{{index .Config.Labels "meu_label"}}' nome_da_imagem

### 35. Lista todas as imagens disponíveis no registro Docker Hub
docker search --no-trunc nome_da_imagem

### 36. Obtém informações de autoria de uma imagem
docker image inspect --format '{{.Author}}' nome_da_imagem

### 37. Exibe informações de nível inferior sobre uma imagem
docker image inspect --format '{{.RootFS.Layers}}' nome_da_imagem

### 38. Exibe o histórico de construção de uma imagem em formato JSON
docker image inspect --format '{{json .RootFS.Layers}}' nome_da_imagem

### 39. Mostra informações sobre o rótulo de versão da API do Docker
docker version --format '{{.Server.Version}}'

### 40. Define uma variável de ambiente em um contêiner em execução
docker exec -e VARIAVEL=valor meu_contêiner

## 3. Gerenciando Contêineres

### 1. Inicia um novo contêiner a partir de uma imagem
docker run nome_da_imagem

### 2. Inicia um novo contêiner em segundo plano (detach mode)
docker run -d nome_da_imagem

### 3. Inicia um contêiner interativamente e entra no shell
docker run -it nome_da_imagem

### 4. Inicia um contêiner com um nome personalizado
docker run --name meu_contêiner nome_da_imagem

### 5. Inicia um contêiner com uma variável de ambiente
docker run -e VARIAVEL=valor nome_da_imagem

### 6. Inicia um contêiner com mapeamento de porta (host:container)
docker run -p 8080:80 nome_da_imagem

### 7. Inicia um contêiner e monta um volume (bind mount)
docker run -v /caminho/local:/caminho/no/contêiner nome_da_imagem

### 8. Inicia um contêiner e remove-o quando ele é parado
docker run --rm nome_da_imagem

### 9. Exibe uma lista de contêineres em execução
docker ps

### 10. Exibe uma lista de todos os contêineres (incluindo parados)
docker ps -a

### 11. Para a execução de um contêiner em execução
docker stop meu_contêiner

### 12. Reinicia um contêiner
docker restart meu_contêiner

### 13. Pausa a execução de um contêiner em execução
docker pause meu_contêiner

### 14. Despausa a execução de um contêiner pausado
docker unpause meu_contêiner

### 15. Executa um comando em um contêiner em execução
docker exec -it meu_contêiner comando

### 16. Exibe logs de um contêiner em execução
docker logs meu_contêiner

### 17. Remove um contêiner (deve ser parado antes)
docker rm meu_contêiner

### 18. Remove todos os contêineres parados
docker container prune

### 19. Executa um comando em um novo contêiner e remove-o após a execução
docker run --rm nome_da_imagem comando

### 20. Exibe informações detalhadas sobre um contêiner
docker inspect meu_contêiner

### 21. Exibe estatísticas em tempo real de um contêiner em execução
docker stats meu_contêiner

### 22. Exibe informações de uso de recursos de um contêiner específico
docker stats --no-stream meu_contêiner

### 23. Copia arquivos ou diretórios do sistema local para um contêiner em execução
docker cp arquivo/diretório meu_contêiner:/caminho/no/contêiner

### 24. Copia arquivos ou diretórios de um contêiner para o sistema local
docker cp meu_contêiner:/caminho/no/contêiner arquivo/diretório

### 25. Mapeia variáveis de ambiente a partir de um arquivo .env para um contêiner
docker run --env-file arquivo.env nome_da_imagem

### 26. Exibe informações de uso de recursos de todos os contêineres em execução
docker stats $(docker ps --format "{{.Names}}")

### 27. Redimensiona um contêiner (altera CPU e memória)
docker update --cpu-shares 512 --memory 512m meu_contêiner

### 28. Define um limite de CPU para um contêiner
docker run --cpus 0.5 nome_da_imagem

### 29. Define um limite de memória para um contêiner
docker run --memory 512m nome_da_imagem

### 30. Exibe as configurações de rede de um contêiner
docker network inspect meu_contêiner

### 31. Exibe informações sobre os volumes montados em um contêiner
docker inspect -f '{{ .Mounts }}' meu_contêiner

### 32. Exibe as variáveis de ambiente de um contêiner em execução
docker exec meu_contêiner env

### 33. Anexa ao console de um contêiner em execução
docker attach meu_contêiner

### 34. Gera um arquivo de exportação do contêiner em execução
docker export meu_contêiner > arquivo.tar

### 35. Importa um arquivo de exportação para criar uma imagem
docker import arquivo.tar nome_da_imagem

### 36. Define a prioridade de um contêiner em execução (Windows)
docker update --priority abaixo|normal|acima meu_contêiner

### 37. Exibe os eventos de um contêiner em execução
docker events --filter event=container meu_contêiner

### 38. Move um contêiner de uma rede para outra
docker network disconnect rede_origem meu_contêiner
docker network connect rede_destino meu_contêiner

### 39. Cria um contêiner pausado
docker create --name meu_contêiner nome_da_imagem

### 40. Inicia um contêiner pausado
docker start -a meu_contêiner

## 4. Rede no Docker

### 1. Exibe informações sobre todas as redes no Docker
docker network ls

### 2. Cria uma rede personalizada no Docker
docker network create minha_rede

### 3. Remove uma rede no Docker
docker network rm minha_rede

### 4. Inspect uma rede para obter informações detalhadas
docker network inspect minha_rede

### 5. Conecta um contêiner a uma rede
docker network connect minha_rede meu_contêiner

### 6. Desconecta um contêiner de uma rede
docker network disconnect minha_rede meu_contêiner

### 7. Exibe informações de rede de um contêiner
docker network inspect --format='{{range .IPAM.Config}}{{.Gateway}}{{end}}' meu_contêiner

### 8. Cria um alias de rede para um contêiner
docker network connect --alias meu_alias minha_rede meu_contêiner

### 9. Exibe informações sobre interfaces de rede de contêineres
docker exec meu_contêiner ifconfig

### 10. Mapeia uma porta específica para um contêiner
docker run -p porta_host:porta_contêiner nome_da_imagem

### 11. Exibe as portas mapeadas de um contêiner em execução
docker port meu_contêiner

### 12. Exibe informações de roteamento de rede para um contêiner
docker exec meu_contêiner route

### 13. Cria uma rede overlay para uso em clusters Docker Swarm
docker network create --driver overlay minha_rede_overlay

### 14. Conecta um serviço Docker a uma rede overlay Swarm
docker service update --network-add minha_rede_overlay meu_serviço

### 15. Remove uma rede customizada e seus contêineres associados
docker network prune -f

### 16. Mapeia um intervalo de portas para um contêiner
docker run -p 8080-8090:80 nome_da_imagem

### 17. Exibe informações sobre um driver de rede específico
docker info --format '{{json .NetworkDrivers}}'

### 18. Limita a largura de banda de uma rede
docker network create --subnet 172.18.0.0/16 --opt com.docker.network.bridge.name=my_custom_network --opt com.docker.network.bridge.enable_icc=false minha_rede_customizada

### 19. Inspect uma rede para ver informações sobre os contêineres nela conectados
docker network inspect minha_rede_customizada

### 20. Cria uma rede que permite que contêineres compartilhem o mesmo namespace de rede
docker network create --driver none minha_rede_nenhum_driver

### 21. Lista todas as redes conectadas a um contêiner
docker network ls --filter "container=meu_contêiner"

### 22. Exibe informações detalhadas sobre as interfaces de rede de um contêiner
docker exec meu_contêiner ip a

### 23. Exibe informações sobre as redes conectadas a um contêiner específico
docker inspect --format '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' meu_contêiner

### 24. Conecta automaticamente um contêiner a todas as redes disponíveis
docker run --network="container:meu_contêiner" nome_da_imagem

### 25. Define uma rede personalizada para um contêiner durante a execução
docker run --network=minha_rede nome_da_imagem

### 26. Remove um alias de rede de um contêiner
docker network disconnect --alias meu_alias minha_rede meu_contêiner

### 27. Conecta um contêiner a várias redes
docker network connect minha_rede_1 meu_contêiner
docker network connect minha_rede_2 meu_contêiner

### 28. Define o DNS a ser usado por um contêiner
docker run --dns 8.8.8.8 nome_da_imagem

### 29. Define uma rede para usar endereços IPv6
docker network create --ipv6 minha_rede_ipv6

### 30. Inspect uma rede IPv6 para obter informações detalhadas
docker network inspect --format '{{json .IPAM.Config}}' minha_rede_ipv6

### 31. Conecta um contêiner a uma rede IPv6
docker network connect minha_rede_ipv6 meu_contêiner_ipv6

### 32. Exibe informações detalhadas sobre interfaces de rede de um contêiner IPv6
docker exec meu_contêiner_ipv6 ip -6 a

### 33. Remove uma rede IPv6
docker network rm minha_rede_ipv6

### 34. Exibe informações sobre redes bridge, host e null no Docker
docker network inspect bridge
docker network inspect host
docker network inspect none

### 35. Define uma política de filtro de pacotes em uma rede
docker network create --opt "com.docker.network.bridge.enable_ip_masquerade=false" minha_rede_sem_masquerade

### 36. Cria uma rede em modo host, compartilhando o namespace de rede do host
docker network create --driver host minha_rede_host

### 37. Define uma rede com limitação de largura de banda
docker network create --subnet 172.19.0.0/16 --opt "com.docker.network.driver.mtu=1500" minha_rede_largura_banda

### 38. Atualiza as configurações de uma rede personalizada
docker network update --subnet=172.20.0.0/16 minha_rede_customizada

### 39. Desconecta um contêiner de todas as redes
docker network disconnect --force meu_contêiner

### 40. Exibe informações detalhadas sobre uma rede overlay Swarm
docker network inspect minha_rede_overlay

## 5. Armazenamento no Docker

### 1. Exibe informações sobre volumes no Docker
docker volume ls

### 2. Cria um volume no Docker
docker volume create meu_volume

### 3. Remove um volume no Docker
docker volume rm meu_volume

### 4. Inspect um volume para obter informações detalhadas
docker volume inspect meu_volume

### 5. Cria um contêiner e monta um volume nele
docker run -v meu_volume:/caminho/no/contêiner nome_da_imagem

### 6. Cria um volume com driver específico (exemplo: NFS)
docker volume create --driver local \
  --opt type=nfs \
  --opt o=addr=meu_servidor_nfs,rw \
  --opt device=:/caminho/no/servidor/nfs meu_volume_nfs

### 7. Remove todos os volumes não utilizados
docker volume prune

### 8. Mapeia um diretório local para um volume no contêiner
docker run -v /caminho/local:/caminho/no/contêiner nome_da_imagem

### 9. Copia dados de um volume para outro volume
docker run --rm -v meu_volume_origem:/origem -v meu_volume_destino:/destino nome_da_imagem cp -r /origem/* /destino/

### 10. Cria um snapshot de um volume para backup
docker run --rm -v meu_volume:/origem -v $(pwd):/backup nome_da_imagem tar cvf /backup/meu_backup.tar /origem

### 11. Restaura dados de um backup para um volume
docker run --rm -v meu_volume:/destino -v $(pwd):/backup nome_da_imagem tar xvf /backup/meu_backup.tar -C /destino

### 12. Exibe informações de uso de espaço em disco dos volumes
docker system df -v

### 13. Cria um volume para compartilhamento entre serviços em um stack Docker Compose
docker volume create --name=meu_volume_compose

### 14. Define permissões de acesso em um volume
docker run -v meu_volume:/caminho/no/contêiner:ro nome_da_imagem

### 15. Monta um volume de leitura/gravação apenas para um contêiner
docker run -v meu_volume:/caminho/no/contêiner:rw nome_da_imagem

### 16. Inspect um contêiner para ver quais volumes ele está usando
docker inspect --format '{{ .Mounts }}' meu_contêiner

### 17. Copia arquivos de um volume para o sistema local
docker cp meu_contêiner:/caminho/no/contêiner/arquivo.txt /caminho/local/

### 18. Exibe informações sobre um volume especificando seu nome
docker volume inspect meu_volume

### 19. Redefine as opções de um volume (por exemplo, para mudar o driver)
docker volume create --driver novo_driver --opt chave=valor meu_volume_modificado

### 20. Exclui todos os volumes não utilizados, incluindo aqueles com base em filtros
docker volume prune --filter "label=meu_label"

### 21. Exibe informações sobre todos os pontos de montagem de volumes em um contêiner
docker inspect --format '{{json .Mounts}}' meu_contêiner

### 22. Cria um volume com rótulo personalizado
docker volume create --label meu_label meu_volume_rótulo

### 23. Lista volumes com base em rótulos
docker volume ls -qf "label=meu_label"

### 24. Remove volumes com base em rótulos
docker volume rm $(docker volume ls -qf "label=meu_label")

### 25. Mapeia um volume temporário de um contêiner
docker run --rm -v $(pwd):/caminho/no/contêiner nome_da_imagem

### 26. Atualiza um volume para torná-lo somente leitura
docker volume update --read-only meu_volume

### 27. Monta um volume em modo somente leitura em um contêiner
docker run -v meu_volume:/caminho/no/contêiner:ro nome_da_imagem

### 28. Exibe informações sobre o driver de armazenamento padrão do Docker
docker info --format '{{json .Driver}}'

### 29. Lista todos os plugins de volume disponíveis
docker plugin ls

### 30. Instala um novo plugin de volume
docker plugin install nome_do_plugin

### 31. Desativa um plugin de volume
docker plugin disable nome_do_plugin

### 32. Remove um plugin de volume
docker plugin rm nome_do_plugin

### 33. Exibe informações detalhadas sobre um plugin de volume
docker plugin inspect nome_do_plugin

### 34. Lista os drivers de volume disponíveis
docker volume create --driver 

### 35. Redefine a capacidade de um volume (por exemplo, para aumentar o tamanho)
docker volume create --driver local --opt capacity=10GB meu_volume_capacidade

### 36. Define uma prioridade de armazenamento para um volume
docker volume create --driver local --opt priority=high meu_volume_prioridade

### 37. Compartilha um volume entre contêineres em um serviço Docker Compose
docker-compose.yml:
  services:
    meu_serviço:
      volumes:
        - meu_volume:/caminho/no/contêiner

### 38. Executa um contêiner com acesso a um dispositivo de bloco
docker run --device=/dev/sdX nome_da_imagem

### 39. Exibe informações sobre dispositivos de bloco disponíveis
docker info --format '{{json .Devices}}'

### 40. Utiliza dispositivos de bloco para criação de volumes personalizados
docker run -v /dev/sdX:/caminho/no/contêiner/bloco nome_da_imagem


## 6. Docker Compose

### 1. Executa todos os serviços definidos no arquivo docker-compose.yml em segundo plano
docker-compose up -d

### 2. Para a execução de todos os serviços definidos no arquivo docker-compose.yml
docker-compose down

### 3. Exibe os logs de todos os serviços em execução
docker-compose logs

### 4. Exibe os logs de um serviço específico em execução
docker-compose logs meu_serviço

### 5. Constrói ou reconstrói os serviços definidos no arquivo docker-compose.yml
docker-compose build

### 6. Inicia os serviços definidos no arquivo docker-compose.yml em primeiro plano (para observar os logs)
docker-compose up

### 7. Inicia um serviço específico definido no arquivo docker-compose.yml
docker-compose up meu_serviço

### 8. Para a execução de um serviço específico definido no arquivo docker-compose.yml
docker-compose stop meu_serviço

### 9. Reinicia um serviço específico definido no arquivo docker-compose.yml
docker-compose restart meu_serviço

### 10. Exibe o status dos serviços definidos no arquivo docker-compose.yml
docker-compose ps

### 11. Exibe informações sobre a configuração dos serviços definidos no arquivo docker-compose.yml
docker-compose config

### 12. Escala um serviço para um número específico de réplicas
docker-compose up -d --scale meu_serviço=3

### 13. Exibe informações sobre volumes usados pelos serviços
docker-compose volume ls

### 14. Remove todos os contêineres, redes e volumes associados aos serviços
docker-compose down --volumes

### 15. Remove todos os contêineres, mas mantém redes e volumes
docker-compose down --rmi all

### 16. Exibe a versão do Docker Compose
docker-compose --version

### 17. Pausa a execução de todos os serviços
docker-compose pause

### 18. Despausa a execução de todos os serviços
docker-compose unpause

### 19. Executa um único comando em um serviço
docker-compose exec meu_serviço comando

### 20. Exibe informações detalhadas sobre os serviços definidos no arquivo docker-compose.yml
docker-compose ps --services

### 21. Cria um arquivo docker-compose.yml com base em um modelo
docker-compose config > docker-compose.yml

### 22. Executa serviços em segundo plano, mas também gera logs em tempo real
docker-compose up -d && docker-compose logs -f

### 23. Força a reconstrução de todos os serviços mesmo se eles não tiverem mudado
docker-compose up -d --build

### 24. Define variáveis de ambiente em um arquivo `.env` para uso no docker-compose.yml
docker-compose --env-file meu_arquivo_env up -d

### 25. Executa um serviço e entra no shell interativo
docker-compose run meu_serviço

### 26. Executa um serviço com a opção `--rm` para remover o contêiner quando ele parar
docker-compose run --rm meu_serviço

### 27. Pausa a execução de um serviço específico
docker-compose pause meu_serviço

### 28. Despausa a execução de um serviço específico
docker-compose unpause meu_serviço

### 29. Escala um serviço específico para um número específico de réplicas
docker-compose up -d --scale meu_serviço=3

### 30. Exibe estatísticas de uso de recursos de todos os serviços
docker-compose top

### 31. Remove serviços parados
docker-compose down --remove-orphans

### 32. Exibe informações detalhadas sobre os volumes usados pelos serviços
docker-compose volume ls

### 33. Exibe informações sobre a rede de um serviço específico
docker-compose network inspect meu_serviço

### 34. Atualiza os serviços após a edição do arquivo docker-compose.yml
docker-compose up -d

### 35. Cria e executa um novo serviço com base em um arquivo Compose diferente
docker-compose -f meu_outro_arquivo_compose.yml up -d

### 36. Exibe informações de uso de espaço em disco dos volumes usados pelos serviços
docker-compose volume df

### 37. Pausa todos os serviços
docker-compose pause

### 38. Despausa todos os serviços
docker-compose unpause

### 39. Exibe informações sobre a configuração dos serviços em formato JSON
docker-compose config --json

### 40. Exibe informações sobre a configuração dos serviços em formato YAML
docker-compose config --yaml


## 7. Docker Swarm (Orquestração)

### 1. Inicia um Docker Swarm
docker swarm init

### 2. Insere um nó de trabalho em um Docker Swarm
docker swarm join --token TOKEN IP_DO_MANAGER:PORTA

### 3. Exibe informações sobre o status do Swarm
docker info

### 4. Cria um serviço em um Docker Swarm
docker service create --name meu_servico nome_da_imagem

### 5. Escala um serviço para um número específico de réplicas
docker service scale meu_servico=3

### 6. Atualiza um serviço com uma nova imagem
docker service update --image nova_imagem:tag meu_servico

### 7. Lista todos os serviços em execução no Swarm
docker service ls

### 8. Lista todas as tarefas (contêineres) de um serviço
docker service ps meu_servico

### 9. Remove um serviço do Swarm
docker service rm meu_servico

### 10. Exibe informações detalhadas sobre um serviço
docker service inspect meu_servico

### 11. Visualiza logs de um serviço
docker service logs meu_servico

### 12. Atualiza a política de escalonamento de um serviço
docker service update --replicas=5 meu_servico

### 13. Cria uma rede personalizada no Swarm
docker network create --driver overlay minha_rede_overlay

### 14. Lista todas as redes no Swarm
docker network ls

### 15. Lista nós de trabalho no Swarm
docker node ls

### 16. Atualiza a descrição de um nó de trabalho
docker node update --label-add meu_label meu_node

### 17. Remove um nó de trabalho do Swarm
docker node rm meu_node

### 18. Promove um nó de trabalho a gerente
docker node promote meu_node

### 19. Define uma restrição de implantação para um serviço
docker service create --name meu_servico --constraint 'node.labels.meu_label==valor' nome_da_imagem

### 20. Executa um comando em um nó de trabalho do Swarm
docker node ssh meu_node

### 21. Remove todos os serviços no Swarm
docker service rm $(docker service ls -q)

### 22. Exibe informações sobre todos os nós no Swarm
docker node inspect $(docker node ls -q)

### 23. Define uma restrição de recursos para um serviço
docker service create --name meu_servico --limit-cpu 0.5 --limit-memory 512m nome_da_imagem

### 24. Lista serviços com base em rótulos
docker service ls --filter "label=meu_label"

### 25. Cria um segredo no Swarm
echo "minha_senha" | docker secret create meu_secreto -

### 26. Lista todos os segredos no Swarm
docker secret ls

### 27. Cria um serviço com segredos
docker service create --name meu_servico --secret meu_secreto nome_da_imagem

### 28. Define um limite de atualização para um serviço
docker service update --update-delay 10s --update-parallelism 2 meu_servico

### 29. Lista todas as configurações no Swarm
docker config ls

### 30. Cria uma configuração no Swarm
echo "minha_configuracao" | docker config create meu_configuracao -

### 31. Cria um serviço com configurações
docker service create --name meu_servico --config source=meu_configuracao,target=/caminho/no/contêiner nome_da_imagem

### 32. Remove um segredo do Swarm
docker secret rm meu_secreto

### 33. Remove uma configuração do Swarm
docker config rm meu_configuracao

### 34. Atualiza uma configuração no Swarm
docker config update meu_configuracao

### 35. Atualiza um segredo no Swarm
docker secret update meu_secreto

### 36. Exibe informações detalhadas sobre um nó de trabalho
docker node inspect meu_node

### 37. Exibe informações detalhadas sobre um serviço em formato JSON
docker service inspect --format '{{json .}}' meu_servico

### 38. Atualiza um serviço com uma nova política de restart
docker service update --update-failure-action=rollback meu_servico

### 39. Define uma restrição de implantação baseada em afinidade
docker service create --name meu_servico --constraint 'node.affinity==meu_node' nome_da_imagem

### 40. Cria uma rede overlay com opções personalizadas
docker network create --driver overlay --opt encrypted=true minha_rede_overlay

## 8. Segurança e Boas Práticas

### 1. Atualiza o Docker para a versão mais recente
docker-compose down
docker-compose up -d

### 2. Verifica as vulnerabilidades nas imagens Docker
docker scan nome_da_imagem

### 3. Usa contêineres efêmeros (que não persistem após a execução)
docker run --rm nome_da_imagem

### 4. Restringe as capacidades do kernel em contêineres (e.g., exclui CAP_SYS_ADMIN)
docker run --cap-drop SYS_ADMIN nome_da_imagem

### 5. Usa imagens oficiais e confiáveis do Docker Hub
docker pull imagem_oficial

### 6. Mantém as imagens e contêineres atualizados com correções de segurança
docker-compose pull
docker-compose up -d

### 7. Limita recursos de CPU e memória para evitar ataques de exaustão
docker run --cpu-quota=50000 --memory=512m nome_da_imagem

### 8. Utiliza namespaces de rede para isolar contêineres
docker run --network=none nome_da_imagem

### 9. Evita rodar contêineres com privilégios (privileged)
docker run --privileged=false nome_da_imagem

### 10. Remove contêineres e imagens não utilizados regularmente
docker container prune
docker image prune -a

### 11. Utiliza Docker Content Trust para verificar a autenticidade das imagens
export DOCKER_CONTENT_TRUST=1

### 12. Define limites de recursos (cgroups) para contêineres
docker run --cpu-shares=512 --memory=512m nome_da_imagem

### 13. Usa seccomp (Security-Enhanced Linux) para limitar chamadas ao sistema
docker run --security-opt seccomp=./meu_profile_seccomp.json nome_da_imagem

### 14. Remove caches de imagem após a instalação de pacotes (para reduzir tamanho)
docker run --rm -it --entrypoint /bin/bash nome_da_imagem -c "apt-get update && apt-get install pacote && apt-get clean"

### 15. Evita armazenar senhas e chaves dentro de contêineres (use variáveis de ambiente)
docker run -e MINHA_VARIAVEL_SENHA=senha_secreta nome_da_imagem

### 16. Protege a API Docker com autenticação (usando TLS e autenticação baseada em certificados)
### Configuração detalhada: https://docs.docker.com/engine/security/https/

### 17. Use networks internas para isolar contêineres
docker network create --internal minha_rede_interna

### 18. Use volumes para armazenar dados persistentes fora de contêineres
docker run -v /meu/volume:/caminho/no/contêiner nome_da_imagem

### 19. Use Docker Bench Security para verificar a configuração de segurança do host Docker
docker run -it --net host --pid host --cap-add audit_control \
  -e DOCKER_CONTENT_TRUST=$DOCKER_CONTENT_TRUST \
  -v /var/lib:/var/lib -v /var/run/docker.sock:/var/run/docker.sock \
  --label docker_bench_security \
  docker/docker-bench-security

### 20. Monitore os registros de auditoria do kernel para atividades suspeitas
docker run --privileged --pid=host -v /var/log:/var/log -it --net=host debian:jessie /bin/bash

### 21. Use uma ferramenta de varredura de vulnerabilidades de terceiros
docker run -it --net=host -v /var/run/docker.sock:/var/run/docker.sock \
  aquasec/trivy nome_da_imagem

### 22. Implemente políticas de segurança com Docker Content Trust
docker run --rm -it -v $HOME/.docker/trust:/root/.docker/trust \
  docker/content-trust sign nome_da_imagem:tag

### 23. Use chaves SSH individuais ao clonar repositórios privados dentro de contêineres
docker run -v $HOME/.ssh:/root/.ssh nome_da_imagem

### 24. Use namespaces de usuário para restringir privilégios
docker run --user 1000:1000 nome_da_imagem

### 25. Restrinja a exposição de portas apenas às necessárias
docker run -p 80:80 nome_da_imagem

### 26. Limite o tempo de vida dos tokens de autenticação em imagens privadas
docker login -e 1h

### 27. Use a opção `--read-only` para montar sistemas de arquivos em modo somente leitura
docker run --read-only nome_da_imagem

### 28. Use imagens baseadas em alpine para reduzir a superfície de ataque
### Exemplo: alpine:3.14
docker run alpine:3.14

### 29. Atualize regularmente as imagens base para aplicar patches de segurança
docker pull alpine:3.15
docker run alpine:3.15

### 30. Evite expor sockets Docker no contêiner
docker run -v /var/run/docker.sock:/var/run/docker.sock nome_da_imagem

### 31. Use o Docker Security Scanning para verificar imagens em busca de vulnerabilidades
### Disponível em alguns registros Docker comerciais

### 32. Aplique o princípio do mínimo privilégio ao conceder permissões
### Evite usar a opção --privileged ou dar acesso à API Docker desnecessariamente

### 33. Evite usar imagens não verificadas ou não oficiais em produção

### 34. Monitore constantemente as atualizações de segurança do Docker e do sistema operacional

### 35. Realize testes regulares de penetração e auditorias de segurança em seus aplicativos Docker


## 9. Monitoramento e Gerenciamento 

### 1. Exibe informações de uso de recursos de contêineres em execução
docker stats

### 2. Exibe informações detalhadas sobre o uso de recursos de um contêiner específico
docker stats meu_contêiner

### 3. Exibe as 10 principais estatísticas de uso de recursos de contêineres
docker stats --no-stream --format "table {{.Container}}\t{{.Name}}\t{{.CPUPerc}}\t{{.MemUsage}}"

### 4. Monitora os logs de um contêiner em tempo real
docker logs -f meu_contêiner

### 5. Monitora os logs de vários contêineres de um serviço
docker-compose logs -f meu_serviço

### 6. Inspeciona os eventos do Docker em tempo real
docker events

### 7. Exibe informações detalhadas sobre o uso de recursos do sistema Docker
docker system df

### 8. Limpa contêineres parados, imagens não utilizadas e volumes não utilizados
docker system prune -a

### 9. Exibe informações sobre os processos dentro de um contêiner
docker top meu_contêiner

### 10. Exibe as últimas N linhas dos logs de um contêiner
docker logs --tail N meu_contêiner

### 11. Monitora o uso de recursos e os processos em um contêiner em execução
docker exec -it meu_contêiner top

### 12. Visualiza os detalhes da configuração de um serviço em um Docker Swarm
docker service ps meu_serviço

### 13. Monitora o uso de recursos de nós de trabalho no Docker Swarm
docker node ps

### 14. Exibe informações sobre os serviços em execução no Docker Swarm
docker service ls

### 15. Monitora a atividade da rede de um contêiner em execução
docker exec -it meu_contêiner tcpdump -i eth0

### 16. Exibe informações detalhadas sobre a configuração de um contêiner
docker inspect meu_contêiner

### 17. Gera um dump de diagnóstico para um contêiner em execução
docker exec meu_contêiner docker-containerd-ctr --namespace moby container export meu_contêiner meu_dump.tar

### 18. Exibe informações sobre o uso de armazenamento de contêineres
docker container diff meu_contêiner

### 19. Exibe informações sobre contêineres em execução, incluindo consumo de CPU e memória
docker container stats

### 20. Monitora o uso de CPU e memória de contêineres em execução com filtragem por nome
docker container stats $(docker ps --format={{.Names}})

### 21. Exibe informações sobre as redes disponíveis no sistema Docker
docker network ls

### 22. Exibe informações detalhadas sobre uma rede específica
docker network inspect minha_rede

### 23. Monitora o tráfego de rede de um contêiner em execução
docker exec -it meu_contêiner tcpdump -i eth0 -n

### 24. Visualiza os logs de um serviço específico no Docker Swarm
docker service logs meu_serviço

### 25. Inspecta o uso de recursos de um nó de trabalho no Docker Swarm
docker node inspect meu_nó

### 26. Define um limite de uso de CPU para um contêiner em execução
docker update --cpus 2 meu_contêiner

### 27. Monitora o uso de CPU e memória de contêineres em execução em formato JSON
docker stats --no-stream --format "table {{json .}}"

### 28. Exibe informações sobre as imagens armazenadas localmente
docker image ls

### 29. Remove imagens não utilizadas
docker image prune

### 30. Exibe informações sobre os volumes criados
docker volume ls

### 31. Exclui volumes não utilizados
docker volume prune

### 32. Lista os dispositivos de bloco disponíveis no sistema
docker info --format '{{json .Driver.Status.Devices}}'

### 33. Exibe informações sobre os recursos do sistema Docker
docker system info

### 34. Exibe informações sobre as configurações do Docker
docker info

### 35. Monitora o uso de disco de contêineres em execução
docker exec meu_contêiner df -h

### 36. Reinicia um serviço em um Docker Swarm
docker service update --force meu_serviço

### 37. Exibe a versão do Docker
docker --version

### 38. Exibe informações detalhadas sobre a configuração do Docker Compose
docker-compose config

### 39. Exibe informações sobre a pilha de serviços em execução no Docker Swarm
docker stack ps minha_pilha

### 40. Verifica a integridade do sistema Docker
docker system check

## 10. Integração com outras Tecnologias

### 1. Inicia um contêiner MySQL com uma senha de root personalizada
docker run --name meu-mysql -e MYSQL_ROOT_PASSWORD=minha_senha -d mysql:latest

### 2. Conecta-se a um contêiner MySQL em execução usando o cliente MySQL
docker exec -it meu-mysql mysql -uroot -pminha_senha

### 3. Exporta um banco de dados MySQL de um contêiner para um arquivo SQL local
docker exec meu-mysql mysqldump -uroot -pminha_senha meu_banco_de_dados > backup.sql

### 4. Importa um arquivo SQL local para um banco de dados MySQL em execução em um contêiner
docker exec -i meu-mysql mysql -uroot -pminha_senha meu_banco_de_dados < backup.sql

### 5. Inicia um contêiner Redis em segundo plano
docker run --name meu-redis -d redis:latest

### 6. Conecta-se a um contêiner Redis em execução usando o cliente Redis
docker exec -it meu-redis redis-cli

### 7. Inicia um contêiner MongoDB com autenticação
docker run --name meu-mongo -d -e MONGO_INITDB_ROOT_USERNAME=root -e MONGO_INITDB_ROOT_PASSWORD=minha_senha mongo:latest

### 8. Conecta-se a um contêiner MongoDB em execução usando o cliente mongo
docker exec -it meu-mongo mongo -u root -p minha_senha

### 9. Inicia um contêiner Elasticsearch em segundo plano
docker run --name meu-elasticsearch -d -e "discovery.type=single-node" docker.elastic.co/elasticsearch/elasticsearch:7.10.0

### 10. Inicia um contêiner Kibana em segundo plano, conectado ao Elasticsearch
docker run --name meu-kibana -d --link meu-elasticsearch:elasticsearch docker.elastic.co/kibana/kibana:7.10.0

### 11. Inicia um contêiner NGINX e mapeia uma porta específica
docker run --name meu-nginx -d -p 8080:80 nginx:latest

### 12. Inicia um contêiner Apache HTTP Server com um arquivo de configuração personalizado
docker run --name meu-apache -d -p 8080:80 -v /caminho/local/httpd.conf:/usr/local/apache2/conf/httpd.conf httpd:latest

### 13. Inicia um contêiner Node.js com base em um diretório local
docker run --name meu-nodejs -d -p 3000:3000 -v /caminho/local/app:/app node:latest

### 14. Inicia um contêiner Python com base em um diretório local
docker run --name meu-python -d -p 5000:5000 -v /caminho/local/app:/app python:latest

### 15. Inicia um contêiner Java com base em um arquivo JAR local
docker run --name meu-java -d -p 8080:8080 -v /caminho/local/meu_app.jar:/app/meu_app.jar openjdk:latest

### 16. Inicia um contêiner Ruby com base em um diretório local
docker run --name meu-ruby -d -p 3000:3000 -v /caminho/local/app:/app ruby:latest

### 17. Inicia um contêiner .NET Core com base em um diretório local
docker run --name meu-dotnet -d -p 5000:5000 -v /caminho/local/app:/app mcr.microsoft.com/dotnet/aspnet:latest

### 18. Inicia um contêiner PHP com base em um diretório local
docker run --name meu-php -d -p 8080:80 -v /caminho/local/app:/var/www/html php:latest

### 19. Inicia um contêiner PostgreSQL com autenticação
docker run --name meu-postgres -d -e POSTGRES_USER=meu_usuario -e POSTGRES_PASSWORD=minha_senha postgres:latest

### 20. Conecta-se a um contêiner PostgreSQL em execução usando o cliente psql
docker exec -it meu-postgres psql -U meu_usuario -d meu_banco_de_dados

### 21. Inicia um contêiner Apache Kafka
docker run -d --name meu-kafka -p 9092:9092 confluentinc/cp-kafka:latest

### 22. Inicia um contêiner Apache ZooKeeper para suportar o Kafka
docker run -d --name meu-zookeeper -p 2181:2181 confluentinc/cp-zookeeper:latest

### 23. Inicia um contêiner PostgreSQL com uma configuração personalizada
docker run -d --name meu-postgres -e POSTGRES_USER=meu_usuario -e POSTGRES_PASSWORD=minha_senha -e POSTGRES_DB=meu_banco_de_dados -p 5432:5432 postgres:latest

### 24. Inicia um contêiner MySQL com uma configuração personalizada
docker run -d --name meu-mysql -e MYSQL_ROOT_PASSWORD=minha_senha -e MYSQL_DATABASE=meu_banco_de_dados -p 3306:3306 mysql:latest

### 25. Inicia um contêiner WordPress, conectado a um contêiner MySQL
docker run -d --name meu-wordpress -e WORDPRESS_DB_HOST=meu-mysql -e WORDPRESS_DB_USER=root -e WORDPRESS_DB_PASSWORD=minha_senha -p 8080:80 wordpress:latest

### 26. Inicia um contêiner MongoDB com autenticação
docker run -d --name meu-mongodb -e MONGO_INITDB_ROOT_USERNAME=root -e MONGO_INITDB_ROOT_PASSWORD=minha_senha -p 27017:27017 mongo:latest

### 27. Inicia um contêiner Couchbase Server com configurações personalizadas
docker run -d --name meu-couchbase -p 8091-8094:8091-8094 -p 11210:11210 -e COUCHBASE_ROOT_PASSWORD=minha_senha couchbase:latest

### 28. Inicia um contêiner Elasticsearch e o conecta a um contêiner Kibana
docker run -d --name meu-elasticsearch -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" docker.elastic.co/elasticsearch/elasticsearch:7.10.0

### 29. Inicia um contêiner Kibana conectado ao Elasticsearch
docker run -d --name meu-kibana --link meu-elasticsearch:elasticsearch -p 5601:5601 docker.elastic.co/kibana/kibana:7.10.0

### 30. Inicia um contêiner Redis Sentinel para alta disponibilidade
docker run -d --name meu-redis-sentinel --link meu-redis:meu-redis -p 26379:26379 redis:latest redis-server --sentinel announce-ip meu-redis --sentinel announce-port 6379

### 31. Inicia um contêiner RabbitMQ com configurações personalizadas
docker run -d --name meu-rabbitmq -p 5672:5672 -p 15672:15672 -e RABBITMQ_DEFAULT_USER=meu_usuario -e RABBITMQ_DEFAULT_PASS=minha_senha rabbitmq:latest

### 32. Inicia um contêiner Nginx como proxy reverso para outros serviços
docker run -d --name meu-proxy-reverso -p 80:80 -v /caminho/local/nginx.conf:/etc/nginx/nginx.conf nginx:latest

### 33. Inicia um contêiner Prometheus para monitoramento
docker run -d --name meu-prometheus -p 9090:9090 prom/prometheus:latest

### 34. Inicia um contêiner Grafana para visualização de métricas
docker run -d --name meu-grafana -p 3000:3000 grafana/grafana:latest

### 35. Inicia um contêiner Jenkins para integração contínua
docker run -d --name meu-jenkins -p 8080:8080 -p 50000:50000 jenkins/jenkins:latest

### 36. Inicia um contêiner SonarQube para análise de código
docker run -d --name meu-sonarqube -p 9000:9000 sonarqube:latest

### 37. Inicia um contêiner GitLab para controle de código-fonte
docker run -d --name meu-gitlab -p 80:80 -p 443:443 -p 22:22 gitlab/gitlab-ce:latest

### 38. Inicia um contêiner Mattermost para comunicação em equipe
docker run -d --name meu-mattermost -p 8065:8065 mattermost/mattermost-team:latest

### 39. Inicia um contêiner Nextcloud para armazenamento e colaboração
docker run -d --name meu-nextcloud -p 8080:80 nextcloud:latest

### 40. Inicia um contêiner WordPress com banco de dados MariaDB
docker run -d --name meu-wordpress -p 8080:80 -e WORDPRESS_DB_HOST=meu-mariadb -e WORDPRESS_DB_USER=root -e WORDPRESS_DB_PASSWORD=minha_senha wordpress:latest

## 11. Resolução de Problemas

### 1. Exibe os logs de um contêiner em tempo real para diagnóstico
docker logs -f meu_contêiner

### 2. Executa um contêiner em modo interativo para depurar problemas
docker run -it meu_contêiner /bin/bash

### 3. Exibe informações sobre a configuração do Docker
docker info

### 4. Exibe detalhes sobre um erro específico do Docker
docker info --format '{{.Debug}}'

### 5. Verifica a conectividade de rede entre contêineres
docker exec -it meu_contêiner ping outro_contêiner

### 6. Verifica se um serviço em um Docker Swarm está funcionando
docker service ps meu_serviço

### 7. Verifica os eventos do Docker para identificar problemas
docker events

### 8. Verifica a utilização de recursos do sistema por contêineres
docker stats

### 9. Reinicia o Docker para resolver problemas de serviço
systemctl restart docker

### 10. Remove todos os contêineres parados para liberar recursos
docker container prune

### 11. Remove todas as imagens não utilizadas para economizar espaço em disco
docker image prune -a

### 12. Remove todos os volumes não utilizados para liberar espaço de armazenamento
docker volume prune

### 13. Verifica os logs de inicialização do Docker para problemas
journalctl -u docker

### 14. Verifica as configurações do daemon Docker
docker info --format '{{.Runtimes}}'

### 15. Exibe informações detalhadas sobre um contêiner para solucionar problemas
docker inspect meu_contêiner

### 16. Verifica as redes disponíveis no sistema Docker
docker network ls

### 17. Lista os nós de trabalho em um Docker Swarm para identificar falhas
docker node ls

### 18. Remove um serviço em um Docker Swarm para reconstruir
docker service rm meu_serviço

### 19. Verifica se as portas necessárias estão acessíveis em um contêiner
docker exec -it meu_contêiner nc -zv outro_contêiner 80

### 20. Analisa os logs de erro do Docker para solucionar problemas
docker events --filter 'event=error'

### 21. Verifica as configurações do daemon Docker para erros
docker daemon --debug

### 22. Força a remoção de um contêiner em execução
docker rm -f meu_contêiner

### 23. Exibe os processos em execução dentro de um contêiner para diagnóstico
docker top meu_contêiner

### 24. Lista todos os contêineres em execução
docker ps

### 25. Exibe informações detalhadas sobre um serviço em um Docker Swarm
docker service inspect meu_serviço

### 26. Visualiza os logs de um serviço específico no Docker Swarm
docker service logs meu_serviço

### 27. Inspecta a rede de sobreposição em um Docker Swarm
docker network inspect rede_de_sobreposicao

### 28. Força a atualização de um serviço em um Docker Swarm
docker service update --force meu_serviço

### 29. Limpa o cache DNS interno do Docker para resolver problemas de resolução de nomes
docker network prune

### 30. Exibe informações sobre as tarefas de serviço em um Docker Swarm
docker service ps meu_serviço

### 31. Exibe informações sobre as redes de serviço em um Docker Swarm
docker service inspect --format '{{json .Endpoint.VirtualIPs}}' meu_serviço

### 32. Verifica o status de todos os serviços em execução em um Docker Swarm
docker service ls

### 33. Exibe as configurações de montagem de volumes de um contêiner
docker inspect -f '{{json .Mounts}}' meu_contêiner

### 34. Inspeciona a configuração de rede de um contêiner
docker network inspect $(docker inspect -f '{{.NetworkSettings.Networks.<nome_da_rede>.NetworkID}}' meu_contêiner)

### 35. Verifica a configuração do firewall no host para permitir tráfego Docker
iptables -L -n

### 36. Exibe as variáveis de ambiente definidas em um contêiner
docker exec meu_contêiner env

### 37. Força a remoção de todos os contêineres parados
docker rm $(docker ps -a -q)

### 38. Exibe as informações de erro da última execução do Docker
docker info --format '{{.Debug}}'

### 39. Verifica se o daemon Docker está em execução e responde
docker info

### 40. Verifica se o Docker está em execução no modo Swarm
docker info --format '{{.Swarm.LocalNodeState}}'



