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


