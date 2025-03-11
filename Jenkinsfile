pipeline {
    agent any
    tools {
        maven 'maven'
    }
    stages {
        stage ('clean'){
        steps {
            sh 'mvn clean'
        }
        }
        stage ('validate') {
        steps {
            sh 'mvn validate'
        }
        }
        stage ('compile') {
        steps {
            sh 'mvn compile'
        }
        }
        stage ('package') {
        steps {
            sh 'mvn package'
        }
        }
        stage ('into nexus') {
            steps {
                sh 'mvn -s settings.xml clean deploy'
            }
            post {
                success {
                    echo "always"
                }
                failure {
                    echo "failure"
                }

            }
        }
    }
    post {
        always {
            echo "always"
        }
        success {
            echo "success"
        }
        failure {
            echo "failure"
        }
    }
}