install: build release deploy test

build:
	docker build --tag ciiru/node-server .

run:
	docker run -d --name labrecap -p 8080:80 ciiru/node-server

release:
	docker push ciiru/node-server

deploy:
	kubectl -n labrecap apply -f ./k8s

delete:
	kubectl -n labrecap delete -f ./k8s

test:
	@echo "Running tests -- may take a few seconds"
	@./test.sh > /dev/null
	@echo "Passed"
