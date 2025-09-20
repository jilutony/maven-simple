pipeline {
    agent any

    environment {
        REPO_URL = 'https://github.com/jilutony/maven-simple.git'
    }

    stages {
        stage('Build') {
            steps {
                sh 'mvn -B package --file pom.xml'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
                echo "scan has been only applied to new branch"
            }
        }
    }
}
