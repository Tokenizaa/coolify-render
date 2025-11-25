# Coolify

Self-hosted PaaS similar to Heroku or Netlify

## Descrição

Coolify é uma plataforma de código aberto e auto-hospedável que permite implantar e gerenciar aplicações, bancos de dados e serviços em seus próprios servidores via SSH. É uma alternativa ao Heroku, Netlify e Vercel, oferecendo controle total sobre a infraestrutura.

## Características Principais

- **Implantação Automática**: Integração com Git para implantação contínua
- **Gerenciamento de Servidores**: Suporte a VPS, servidores bare metal e Raspberry Pis
- **Bancos de Dados**: Suporte a PostgreSQL, MySQL, MongoDB, Redis e outros
- **Proxy Reverso**: Configuração automática de Nginx ou Traefik
- **SSL Automático**: Certificados SSL gratuitos via Let's Encrypt
- **Monitoramento**: Monitoramento de recursos e notificações
- **Backups**: Sistema de backup automatizado para bancos de dados

## Tecnologias Utilizadas

- **Backend**: Laravel 12 (PHP 8.4)
- **Frontend**: Livewire 3.5+ com Alpine.js e Tailwind CSS 4.1+
- **Banco de Dados**: PostgreSQL 15 (principal), Redis 7 (cache/filas)
- **Real-time**: Soketi (servidor WebSocket)
- **Containerização**: Docker & Docker Compose
- **Gerenciamento de Filas**: Laravel Horizon

## Integração com n8n MCP

Este projeto inclui integração com o n8n através do protocolo MCP (Model Connector Protocol), permitindo a automação de workflows e a integração com assistentes de IA.

### Configuração do MCP no n8n

O acesso MCP ao n8n já está configurado:

- **URL do servidor MCP**: `https://n8n.lojaon.shop/mcp-server/http`
- **Token de acesso**: `eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiI0MWNjMTZkOS1lOWQ2LTRlYmUtYTFkMy1jNzQ5OGM5ZGZlNDUiLCJpc3MiOiJuOG4iLCJhdWQiOiJtY3Atc2VydmVyLWFwaSIsImp0aSI6Ijk0MDM3MDk1LTI3MDYtNDViNS1iOTQyLTU2NjA3MjBhNWVjNCIsImlhdCI6MTc2NDExMzQzM30.nTdzTdva_66XpZGKzkOdQZndYF0VxSj-OQmUzvrHufE`

### Como usar com Claude Desktop

Para conectar este projeto ao Claude Desktop, adicione a seguinte configuração ao seu arquivo `claude.json`:

```json
{
  "mcpServers": {
    "n8n-local": {
      "type": "http",
      "url": "https://n8n.lojaon.shop/mcp-server/http",
      "headers": {
        "Authorization": "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiI0MWNjMTZkOS1lOWQ2LTRlYmUtYTFkMy1jNzQ5OGM5ZGZlNDUiLCJpc3MiOiJuOG4iLCJhdWQiOiJtY3Atc2VydmVyLWFwaSIsImp0aSI6Ijk0MDM3MDk1LTI3MDYtNDViNS1iOTQyLTU2NjA3MjBhNWVjNCIsImlhdCI6MTc2NDExMzQzM30.nTdzTdva_66XpZGKzkOdQZndYF0VxSj-OQmUzvrHufE"
      }
    }
  }
}
```

## Workflows Disponíveis

Para utilizar os workflows, é necessário habilitá-los individualmente nas configurações de cada fluxo no n8n.

## Mais Informações

- [Documentação do Coolify](https://coolify.io/docs)
- [Documentação do n8n MCP](https://docs.n8n.io/advanced-ai/accessing-n8n-mcp-server/)
