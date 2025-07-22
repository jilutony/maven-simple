pipeline {
    agent any

    environment {
        REPO_URL = 'https://github.com/jilutony/maven-simple.git'
    }

    stages {
        stage('Checkout') {
            steps {
                git url: "${REPO_URL}", branch: 'master'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn -B package --file pom.xml'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}
