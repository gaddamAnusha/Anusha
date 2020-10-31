pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'mvn compile'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh 'git --version'
                sh 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                sh 'java -version'
                sh 'mvn package'
            }
        }
        stage('release') {
            agent { label 'master' }
            steps {
               sh "printenv | sort"
            }
        }
    }
}
