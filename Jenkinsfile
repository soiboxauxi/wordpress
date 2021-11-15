node {

	//Define all variables
	def project = 'wordpress-app'
	def imageVersion = 'v2.0'
	def namespace = "${namespace_gui}"
	def imageTag = "wordpress:v5.8.2"

	//Checkout Code from Git
	checkout scm

	//Build the docker image.
    stage('Build image') {
        sh("docker login -u $DOCKER_USERNAME -p $DOCKER_PASSWORD")
        sh("docker build -t $DOCKER_USERNAME/${imageTag} wordpress-app/.")
    }

    //Push the image to docker registry
    stage('Push image to registry') {
        sh("docker push $DOCKER_USERNAME/${imageTag}")
    }
}