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



