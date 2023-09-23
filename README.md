# Repositório com comandos Uteis do Docker

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

