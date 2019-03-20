SERVICE="go-mod-server"
VERSION=`date +%Y%m%d`-1 

deploy:
	docker build -t ${SERVICE}:${VERSION} .
	-docker stop ${SERVICE}
	-docker rm ${SERVICE}
	docker run --log-opt max-size=10m --log-opt max-file=10 --name ${SERVICE} -d --restart=always -p 8080:8080 ${SERVICE}:${VERSION}

logs:
	docker logs ${SERVICE} 2>&1

stats:
	docker stats ${SERVICE}

restart:
	docker restart ${SERVICE}

