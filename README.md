# RabbitMQ Lab - Sistema de Processamento de Pedidos

Projeto de aprendizado de RabbitMQ com Python, FastAPI e Docker.

## Estrutura do Projeto

```
rabbitmq-lab/
├── api/              # API REST (FastAPI)
├── workers/          # Consumers (Workers Python)
├── config/           # Configurações compartilhadas
├── docker-compose.yml
├── requirements.txt
└── .env
```

## Passo 1: Configurar e Subir o RabbitMQ

### 1. Certifique-se que o Docker Desktop está rodando no seu Mac

### 2. Navegue até a pasta do projeto e suba o RabbitMQ:

```bash
cd rabbitmq-lab
docker-compose up -d
```

O `-d` roda em modo detached (background)

### 3. Verifique se o container está rodando:

```bash
docker ps
```

Você deve ver um container chamado `rabbitmq-lab` com status "Up"

### 4. Aguarde alguns segundos para o RabbitMQ inicializar completamente

### 5. Acesse a interface de gerenciamento:

Abra no navegador: http://localhost:15672

Credenciais:
- **Usuário**: admin
- **Senha**: admin123

### 6. Explore a interface:

- **Overview**: Visão geral do servidor
- **Connections**: Conexões ativas
- **Channels**: Canais de comunicação
- **Exchanges**: Veja os exchanges padrão
- **Queues**: Lista de filas (ainda vazia)

### Comandos Úteis:

```bash
# Ver logs do RabbitMQ
docker-compose logs -f rabbitmq

# Parar o RabbitMQ
docker-compose down

# Parar e remover dados (cuidado!)
docker-compose down -v
```

## Próximos Passos

Após confirmar que o RabbitMQ está rodando e você conseguiu acessar a interface web, estamos prontos para:
- Criar um módulo de conexão Python
- Implementar o primeiro producer simples
