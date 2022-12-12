pipeline {
    agent any

    stages {
        stage('git checkout') {
            steps {
                git credentialsId: '9cdca2ad-b9f3-4258-9065-da9bbc66a241', url: 'https://github.com/Swillam/java-docker'
            }
        }
        
         stage('Build the application') {
            steps {
                sh 'mvn clean install'
            }
        }
        stage('Unit Test Execution') { 
            steps{
                sh 'mvn test'
            }
        }
        stage('Build the docker image') { 
            steps{
                sh "docker build -t shawnmodestine/jenkins_triangle:1.0.0 ."
            }
        }
        stage('Push the docker image') {
            steps{
                withCredentials([string(credentialsId: 'dockerhubpass', variable: 'dockerHubPass')]) {
                    sh "docker login -u shawnmodestine -p $dockerHubPass  docker.io"
                }
                sh 'docker push shawnmodestine/jenkins_triangle:1.0.0'
            } 
        }
    }
}
