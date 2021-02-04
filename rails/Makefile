build:
	docker-compose run web bundle install
	docker-compose up -d --build

run:
	docker-compose up -d

create_db: run
	docker-compose run web rake db:create

migrate_db: run
	docker-compose run web rake db:migrate

stop:
	docker-compose down
