ENV_FILE_PATH = ./env/.env.local
start:
	docker compose --env-file $(ENV_FILE_PATH) -f docker-compose.yml up -d;

stop:
	docker compose --env-file $(ENV_FILE_PATH) -f docker-compose.yml stop;

show_containers:
	docker compose --env-file $(ENV_FILE_PATH) -f docker-compose.yml ps;

restart: stop start

build:
	docker compose --env-file $(ENV_FILE_PATH) -f docker-compose.yml build;

down:
	docker compose --env-file $(ENV_FILE_PATH) -f docker-compose.yml down;
	docker compose --env-file $(ENV_FILE_PATH) -f docker-compose.yml down --rmi all --volumes;