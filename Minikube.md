# Install Minikube in Windows use cmd/power shell (Administrator permission)
	Install Choco: https://chocolatey.org/packages/chocolatey
		choco install chocolatey
		choco upgrade chocolatey
	
	Install Minikube by Choco: https://chocolatey.org/packages/Minikube
		choco install minikube
		choco upgrade minikube
		
	Run Minikube: https://github.com/kubernetes/minikube
		minikube start
		
# Deploy project to docker: https://docs.docker.com/get-started/part2/#run-the-app
	See "Tag the image".
	Ex:
		docker login -u <username>
		docker tag uaa tronghuynhhb/sandent:uaa
			tronghuynhhb/sandent: my repository
			uaa: tag name
		docker push tronghuynhhb/sandent:uaa : push project to repository docker.
		docker run -p 4000:80 tronghuynhhb/sandent:uaa
