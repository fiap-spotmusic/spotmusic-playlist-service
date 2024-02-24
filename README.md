# SpotMusic - Serviço de Gerenciamento de Playlists

## Visão Geral
Este repositório contém o serviço de gerenciamento de playlists da SpotMusic, que é responsável por operações relacionadas à criação, edição, compartilhamento e gerenciamento de playlists musicais.

## Funcionalidades
- Criação e edição de playlists musicais.
- Compartilhamento de playlists com outros usuários.
- Integração com serviços de streaming de música.
- Gerenciamento de acesso e permissões para playlists colaborativas.
- Recomendações personalizadas de músicas para adicionar às playlists.

## Arquitetura
Este serviço faz parte de uma arquitetura de microserviços e é construído com base em APIs RESTful. Ele é projetado para ser seguro, confiável e facilmente escalável.

## Pilha Tecnológica
- **Linguagem de Programação:** Python com Flask
- **Banco de Dados:** MySQL (Nome do Banco: `spotmusic_playlists`)
- **Fila de Mensagens:** Amazon SQS (Nome da Fila: `spotmusic_playlist_updates`)
- **Monitoramento:** Zabbix

## Configuração e Instalação
Para configurar e executar o `spotmusic-playlist-service` localmente, siga os passos abaixo:

```bash
# Clone o repositório
git clone https://github.com/fiap-spotmusic/spotmusic-playlist-service.git
cd spotmusic-playlist-service

# Instale as dependências
pip install -r requirements.txt

# Copie o arquivo .env.template, cole como .env e substitua as variáveis apontando para o ambiente desejado
cp .env.template .env
# Agora, edite o arquivo .env com as configurações do seu ambiente
nano .env

# Carregue as variáveis de ambiente
export $(cat .env | xargs)

# Execute as migrações para o banco de dados
flask db upgrade

# Inicie o serviço
flask run
