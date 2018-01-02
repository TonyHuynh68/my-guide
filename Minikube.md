# Install Minikube in Windows use cmd/power shell (Administrator permission)
Install Choco: https://chocolatey.org/packages/chocolatey

	Set-ExecutionPolicy Bypass -Scope Process -Force; iwr https://chocolatey.org/install.ps1 -UseBasicParsing | iex
	choco install chocolatey
	choco upgrade chocolatey
	
Install Minikube by Choco: https://chocolatey.org/packages/Minikube

	choco install minikube
	choco upgrade minikube

Run Minikube: https://github.com/kubernetes/minikube

	minikube start
		
# Deploy project to docker
See "Tag the image": https://docs.docker.com/get-started/part2/#run-the-app

Ex:

	docker login -u <username>
	docker tag uaa tronghuynhhb/sandent:uaa
		tronghuynhhb/sandent:uaa <=> username/repository:tag
		uaa: tag name
	docker push tronghuynhhb/sandent:uaa : push project to repository docker.
	docker run -p 4000:80 tronghuynhhb/sandent:uaa

If docker-compose up fail, try this:

	docker rm -f $(docker ps -aq) (will remove all of your containers)
	docker network rm $(docker network ls -q) (will remove all of your networks)
	docker image rm <image id>            # Remove specified image from this machine
	docker image rm $(docker image ls -a -q)   # Remove all images from this machine
	docker run --rm -v /var/lib/docker/network/files:/network busybox rm /network/local-kv.db
	
Then restart Docker for Mac/Window and you should be good to go 👍
