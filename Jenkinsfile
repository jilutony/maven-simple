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
                script {
                    try {
                        sh 'mvn test'
                        currentBuild.description = "Tests Passed"
                        echo "✅ All tests passed successfully."
                    } catch (Exception err) {
                        currentBuild.description = "Tests Failed"
                        echo "❌ Some tests failed. Check the logs for details."
                        throw err // Rethrow to fail the build
                    }
                }
            }
        }
    }
}
