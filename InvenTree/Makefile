PROJECT_NAME = reference_inventree

all:
	@echo clear
	@echo init
	@echo up
	@echo down

clear:
	docker volume rm -f inventree-production_inventree_data
	docker volume rm -f inventree-production_inventree_db

init:
	docker compose run inventree-server invoke update
	docker compose run inventree-server invoke superuser

up:
	docker compose up \
	--project-name $(PROJECT_NAME) \
	-d

down:
	docker compose \
	--project-name $(PROJECT_NAME) \
	down
