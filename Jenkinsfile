pipeline {
    agent {
            label 'pat'
    }
    tools{
        maven 'mymaven'
        jdk 'java'
    }
    stages {
        stage('validate') {
            steps {
                sh 'mvn validate'
            }
        }
        stage('compile') {
            steps {
                sh 'mvn compile'
            }
        }
        stage('test') {
            steps {
                sh 'mvn test'
            }
        }
         stage('package') {
            steps {
                sh 'mvn package'
            }
        }

    }
}
