pipeline {
    agent any
    tools {
        maven 'mymaven'
        jdk 'myjava'
    }
    stages {
        stage('checkout') {
            steps {
                git 'https://github.com/devops-trainer/DevOpsClassCodes.git'
            }
        }
        stage('compile') {
            steps {
                sh 'mvn compile'
            }
        }
        stage('codereview') {
            steps {
                sh 'mvn pmd:pmd'
            }
        }
        stage('unittest') {
            steps {
                sh 'mvn test'
            }
        }
        stage('matrix') {
            steps {
                sh 'mvn cobertura:cobertura'
            }
        }
        stage('package') {
            steps {
                sh 'mvn package'
            }
        }
    }
    
}
