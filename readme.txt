# Para rodar o projeto no console
rackup config.ru -o 0.0.0.0

# Para fazer o build do projeto pelo docker
docker-compose up --build

# Para gerar o banco de dados
docker-compose run --rm website rake db:create

# Para criar migrations
docker-compose run --rm website rake db:create_migration NAME=create_faqs
docker-compose run --rm website rake db:create_migration NAME=create_hashtags
docker-compose run --rm website rake db:create_migration NAME=create_faq_hashtags

# Para rodar as migrations
docker-compose run --rm website rake db:migrate

# Para entrar no console db
docker-compose run --rm website tux